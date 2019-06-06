<template>
	<view class="container">
		<view class="list">
			<view class="fl left">
				<input class="ipt fl" type="text" placeholder="输入新的手机号码" v-model="ipt">
			</view>
			<view class="fr right" :class="{on:ipt.length == 11}">获取验证码</view>
		</view>
		<view class="list">
			<input class="ipt fl" type="text" placeholder="输入验证码">
		</view>
		
		<view class="btn_r">确认修改</view>
		<view class="bgcolor_r"></view>
	</view>
</template>

<script>
	export default{
		data () {
			return{
				ipt:''
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
		font-size: 30upx;
		color: #333;
		line-height: 100upx;
	}
	.list .right{
		color: #666;
	}
	.list .right.on{
		color: #fc921f;
	}
	.list:first-of-type{
		border-bottom: 1upx solid #e5e5e5;
	}
	.list .ipt{
		width: 400upx;
		margin-top: 20upx;
	}

</style>
