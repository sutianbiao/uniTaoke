<template>
	<view class="tk-list">
		<view @click="goShow(item.id)" v-for="(item,index) in list" :key="index" class="tk-item" >
			<view class="tk-item-img-box">
				<img class="tk-item-img" :src="item.imgurl" />
				<view class="tk-juan-price">券￥{{item.juan_money}}</view>
			</view>
			<view class="tk-title">{{item.title}}</view>
			<view class="tk-row-price">
				<text class="tk-price">￥{{item.price}}(券后)</text>
				<text class="tk-sold">销量{{item.sold_num}}</text>
			</view>
		</view>
	</view>
</template>

<script>
	export default{
		name:"taoke-item",
		props:{
			list:{}
		},
		created:function(){
		},
		methods:{
			goShow:function(id){
				uni.navigateTo({
					url:"../../pagestaoke/taoke/show?id="+id
				})
			}
		}
	}
</script>

<style>
.tk-list{
	display: flex;
	flex-direction: row;
	flex-wrap: wrap;
	background-color: #f5f5f5;
}
.tk-item{
	box-sizing: border-box;
	width: 50%;
	color: #666;
	background-color: #fff;
	margin-bottom: 5px;
	padding: 5px;
}
.tk-item-img-box{
	 width:100%;
    height:0px;
    padding-bottom:100%;
    position:relative;
}
.tk-item-img{
	 width:100%;
        height:100%;
        position:absolute;
}
.tk-juan-price{
	position: absolute;
	bottom: 0px;
	right: 0px;
	width: 60px;
	line-height: 20px;
	background-color: #ff4d36;
	color: #fff;
	font-size: 12px;
	text-align: center;
	border-top-left-radius: 10px;
	border-bottom-left-radius: 10px;
}

.tk-title{
	font-size: 14px;
	color: #666;
	width: 100%;
	text-overflow: ellipsis;
	line-height:30px ;
	overflow: hidden;
	white-space: nowrap;
}
.tk-row-price{
	font-size: 12px;
	display: flex;
	flex-direction: row;
}
.tk-price{
	color: #ff4d36;
	flex:1;
}
.tk-sold{
	padding-right: 5px;
	font-size: 12px;
	text-align: right;
}
</style>
