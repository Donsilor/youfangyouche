<template>
	<view class="container">
		<view class="list" v-for="(item, index) in items" :key = index>
			<view class="user">
				<span>{{item.name}}</span>
				<span>{{item.tel}}</span>		
			</view>
			<view class="addr">{{item.address}}</view>
			<view class="box">
				<view class="fl set">设为默认地址</view>
				<view class="fr del">删除</view>
				<view class="fr">编辑</view>
			</view>
		</view>

		
		<navigator class="add_address" url="./new_address">新增收货地址</navigator>

	</view>
</template>

<script>
	export default {
		data() {
			return {
				items:[
					{
						name:'张板栗',
						tel:'18614525252',
						address:'浙江省杭州市滨江区网商路滨江新园区A座609'
					},
					{
						name:'张板栗',
						tel:'18614525252',
						address:'浙江省杭州市滨江区网商路滨江新园区A座609'
					},
					{
						name:'张板栗',
						tel:'18614525252',
						address:'浙江省杭州市滨江区网商路滨江新园区A座609'
					},
					{
						name:'张板栗',
						tel:'18614525252',
						address:'浙江省杭州市滨江区网商路滨江新园区A座609'
					}
				]
			}
		},
		methods: {
			
		}
	}
</script>

<style>
	page{
		background-color: #f5f5f5;
	}
	.container{
		background-color: #f5f5f5;
		padding-bottom: 120upx;
	}
	.container .list{
		width: 100%;
		padding: 30upx 20upx 0;
		box-sizing: border-box;
	}
	.list{
		background-color: #fff;
		margin-bottom: 20upx;
	}
	.list .user{
		font-size: 30upx;
		color: #333;
		font-weight: bold;
	}
	.list .user span{
		margin-right: 20upx;
	}
	.list .addr{
		font-size: 26upx;
		color: #666;
		margin-top: 20upx;
	}
	.list .box{
		width: 100%;
		height: 84upx;
		line-height: 84upx;
		border-top: 1upx solid #f5f5f5;
		margin-top: 30upx;
		font-size: 26upx;
		color: #999;
	}
	.list .box .set{
		color: #f70c12;
	}
	.list .box .del{
		margin-left: 20upx;
	}
	.add_address{
		position: fixed;
		left: 0;
		bottom: 0;
		z-index: 2;
		width: 100%;
		height: 98upx;
		background: linear-gradient(left, #ff8e06, #ff5011);
		background: -webkit-linear-gradient(left, #ff8e06, #ff5011);
		text-align: center;
		line-height: 98upx;
		font-size: 36upx;
		color: #fff;
		letter-spacing: 2upx;
	}
</style>
