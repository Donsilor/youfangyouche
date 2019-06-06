<template>
	<view class="container">
		<view class="tel">
			手机号：<span>186****1717</span>
		</view>
		<view class="list">
			<view class="fl">
				<input type="text" placeholder="请输入验证码">
			</view>
			<view class="fr acquire">获取验证码</view>
		</view>
		<view class="list">
			<input type="text" placeholder="新密码">
		</view>
		<view class="list">
			<input type="text" placeholder="确认密码">
		</view>

		<!-- 确认修改加样式on -->
		<view class="btn_r">确认修改</view>

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
	page{
		background-color: #f5f5f5;
	}
	.tel{
		width: 100%;
		height: 88upx;
		line-height: 88upx;
		font-size: 30upx;
		color: #333;
		padding-left: 20upx;
		box-sizing: border-box;
	}
	.tel span{
		margin-left: 20upx;
	}
	.list{
		width: 100%;
		height: 100upx;
		background-color: #fff;
		padding: 0 20upx;
		box-sizing: border-box;
		border: 1upx solid transparent;
		line-height: 100upx;
		font-size: 30upx;
		color: #999;
		border-bottom: 1upx solid #e5e5e5;
	}
	.list input{
		width: 500upx;
		margin-top: 20upx;
	}
	.list .acquire{
		font-size: 30upx;
		color: #ff5011;
	}
	
	
</style>
