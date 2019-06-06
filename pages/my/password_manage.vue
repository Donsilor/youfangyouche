<template>
	<view class="container">
		<navigator class="list" url="amend_password_login">
			<view class="fl">修改登录密码</view>
			<view class="fr">
				<i class="iconfont icongengduo"></i>
			</view>
		</navigator>
		<navigator class="list" url="amend_password_pay">
			<view class="fl">修改支付密码</view>
			<view class="fr">
				<i class="iconfont icongengduo"></i>
			</view>
		</navigator>

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
	.container{
		padding-top: 20upx;
	}
	.list{
		width: 100%;
		height: 100upx;
		background-color: #fff;
		padding: 0 20upx;
		box-sizing: border-box;
		line-height: 100upx;
		font-size: 30upx;
		color: #333;
		border-bottom: 1upx solid #e5e5e5;
	}
	

</style>
