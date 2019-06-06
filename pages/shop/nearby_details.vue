<template>
	<view class="container">
		<view class="img_box clf">
			<image src="../../static/images/merchant_details_02.png"></image>
		</view>
		<view class="name">{{infomation.name}}</view>
		<view class="list clf">
			<view class="fl left">
				<i class="iconfont icondizhi"></i>
			</view>
			<view class="fr right">{{infomation.address}}</view>
		</view>
		<view class="list clf">
			<view class="fl left">
			</view>
			<view class="fr right">{{infomation.distance}}</view>
		</view>
		<view class="list clf">
			<view class="fl left">
				<i class="iconfont icondianhua"></i>
			</view>
			<view class="fr right">{{infomation.tel}}</view>
		</view>
		
		<view class="footer clf">
			<view class="left fl">
				<view>
					<i class="iconfont icondaohang"></i>
				</view>导航
			</view>
			<view class="right fr">
				<span class="relation">立即联系</span>
				<span>16252522652</span>
			</view>
		</view>
	</view>
</template>

<script>
	export default{
		data () {
			return{
				infomation:{
					name: '深圳度乐龙岗专营店',
					address: '中国浙江省杭州市滨江区网商路699号滨江新园区A座609',
					distance: '距您约2.2km',
					tel: '162 5252 2652'
				}
			}
		}
	}
</script>

<style>
	.img_box{
		width: 100%;
		height: 400upx;
	}
	.img_box image{
		width: 100%;
		height: 100%;
	}
	.name{
		font-size: 30upx;
		color: #333;
		margin: 30upx 20upx;
		font-weight: bold;
	}
	.list{
		padding: 0 20upx;
		box-sizing: border-box;
		margin-bottom: 30upx;
		font-size: 28upx;
		color: #666;
	}
	.list .left{
		width: 40upx;
		text-align: center;
		line-height: 46upx;
		margin-right: 20upx;
	}
	.list .right{
		width: 650upx;
	}
	
	.footer{
		position: fixed;
		left: 0;
		bottom: 0;
		width: 100%;
		height: 98upx;
		background-color: #f5f5f5;
	}
	.footer .left{
		width: 250upx;
		text-align: center;
		font-size: 24upx;
		color: #666;
		padding-top: 12upx;
		box-sizing: border-box;
	}
	.footer .left i{
		font-size: 38upx;
		margin: 20upx 0;
	}
	.footer .right{
		width: 500upx;
		height: 98upx;
		background: linear-gradient(left, #ff8e06, #ff5011);
		text-align: center;
		line-height: 98upx;
		font-size: 32upx;
		color: #fff;
	}
	.footer .right .relation{
		margin-right: 20upx;
	}
</style>
