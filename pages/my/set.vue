<template>
	<view class="container">
		<view class="list header">
			<view class="fl left">头像</view>
			<view class="fr right">
				<view class="img_box">
					<image src="../../static/images/user.png"></image>
				</view>
				<i class="iconfont icongengduo"></i>
			</view>
		</view>
		<navigator class="list" url="./user_name">
			<view class="fl left">用户名</view>
			<view class="fr right">
				<span class="text">今夜月色温柔</span>
				<i class="iconfont icongengduo"></i>
			</view>
		</navigator>
		<navigator class="list" url="./phone_verification">
			<view class="fl left">手机号</view>
			<view class="fr right">
				<span class="text">186****9617</span>
				<i class="iconfont icongengduo"></i>
			</view>
		</navigator>
		<navigator class="list" url="./authentication">
			<view class="fl left">实名认证</view>
			<view class="fr right">
				<span class="text">立即认证</span>
				<i class="iconfont icongengduo"></i>
			</view>
		</navigator>
		<navigator class="list space" url="./password_manage">
			<view class="fl left">密码管理</view>
			<view class="fr right">		
				<i class="iconfont icongengduo"></i>
			</view>
		</navigator>
		<navigator class="list space" url="./about">
			<view class="fl left">关于有车有房</view>
			<view class="fr right">
				<i class="iconfont icongengduo"></i>
			</view>
		</navigator>
		
		<view class="btn_r on">退出登录</view>
		
		<view class="bgcolor_r"></view>
	</view>
</template>

<script>
	export default{
		data () {
			return{
			}
		}
	}
</script>

<style>
	.list{
		width: 100%;
		height: 100upx;
		border-bottom: 1upx solid #e5e5e5;
		background-color: #fff;
		padding: 0 20upx;
		box-sizing: border-box;
		line-height: 100upx;
		font-size: 30upx;
		color: #333;
	}
	.list .left{
		width: 200upx;
		height: 100upx;
		box-sizing: border-box;
		overflow: hidden;
	}
	.list .right{
		width: 400upx;
		height: 100upx;
		box-sizing: border-box;
		overflow: hidden;
		text-align: right;
	}
	.list .text{
		margin-right: 10upx;
	}
	.header{
		height: 160upx;
		line-height: 160upx;
		margin-top: 20upx;
	}
	.header .fr{
		height: 160upx;
	}
	.header .img_box{
		display: inline-block;
		width: 100upx;
		height: 100upx;
		vertical-align: middle;
		border-radius: 50%;
	}
	.header .img_box image{
		width: 100%;
		height: 100%;
		border-radius: 50%;
	}
	.header i{
		display: inline-block;
		vertical-align: middle;
		margin-left: 10upx;
	}
	.space{
		margin-top: 20upx;
	}
	
</style>
