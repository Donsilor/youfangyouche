<template>
	<view class="container">
		<view class="title">请填写实名信息</view>
		<view class="list">
			<view class="fl left">姓名</view>
			<view class="fr right">
				<input class="ipt fr" type="text" placeholder="请输入真实姓名" />
			</view>
		</view>
		<view class="list">
			<view class="fl left">身份证号</view>
			<view class="fr right">
				<input class="ipt fr" type="text" placeholder="请输入真实身份证号" />
			</view>
		</view>
		<view class="list">
			<view class="fl left">银行卡号</view>
			<view class="fr right">
				<input class="ipt fr" type="text" placeholder="请输入提现银行卡号" />
			</view>
		</view>
		
		<!-- 以下全部根据是否认证判断是否显示 -->
		<view class="title">请上传身份证照片</view>
		
		<view class="content">
			<view class="card">
				<image src="../../static/images/card_01.png"></image>
				<input type="text" value="" />
			</view>
			<view class="text">请上传身份证正面</view>
			<view class="card">
				<image src="../../static/images/card_02.png"></image>
			</view>
			<view class="text">请上传身份证反面</view>
			
			<!-- 可点击时加样式on -->
			<view class="btn_r">立即认证</view>
		</view>
		

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
	.title{
		width: 100%;
		height: 76upx;
		background-color: #f5f5f5;
		line-height: 76upx;
		padding-left: 20upx;
		box-sizing: border-box;
		font-size: 28upx;
		color: #999;
	}
	.list{
		width: 100%;
		height: 100upx;
		background-color: #fff;
		line-height: 100upx;
		box-sizing: border-box;
		font-size: 30upx;
		color: #333;
		padding: 0 20upx;
		box-sizing: border-box;
	}
	.list:not(:last-of-type){
		border-bottom: 1upx solid #e5e5e5;
	}
	.list .left{
		width: 200upx;
		height: 100upx;
		box-sizing: border-box;
	}
	.list .right{
		width: 500upx;
		height: 100upx;
		line-height: 100upx;
		box-sizing: border-box;
	}
	.list .right .ipt{
		width: 400upx;
		text-align: right;
		margin-top: 20upx;
	}
	
	.content{
		display: flex;
		flex-direction: column;
		align-items: center;
		text-align: center;
	}
	.content .card{
		width: 522upx;
		height: 332upx;
		margin: 60upx 0 30upx;
	}
	.content .card image{
		width: 100%;
		height: 100%;
	}
	.content .text{
		font-size: 30upx;
		color: #333;
	}
	
	.btn_r{
		margin-bottom: 90upx;
	}
</style>
