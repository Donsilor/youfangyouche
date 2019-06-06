<template>
	<view class="container">
		<view class="img_box">
			<image src="../../static/images/logo_03.png"></image>
		</view>
		<view class="title">有房有车</view>
		<view class="versions">v1.0.0.0</view>
		<view class="updata">检测更新</view>
	</view>
</template>

<script>
</script>

<style>
	.container{
		display: flex;
		flex-direction: column;
		align-items: center;
		text-align: center;
	}
	.img_box{
		width: 180upx;
		height: 180upx;
		margin-top: 100upx;
	}
	.img_box image{
		width: 100%;
		height: 100%;
	}
	.title{
		font-size: 34upx;
		color: #333;
		margin: 30upx 0 20upx;
	}
	.versions{
		font-size: 26upx;
		color: #999;
	}
	.updata{
		width: 140upx;
		height: 50upx;
		border: 1upx solid #fc921f;
		border-radius: 5upx;
		font-size: 26upx;
		color: #fc921f;
		text-align: center;
		line-height: 50upx;
		margin-top: 20upx;
	}
</style>
