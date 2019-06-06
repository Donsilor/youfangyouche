<template>
	<view class="container">
		<view class="user_img">
			<image src="../../static/images/user.png"></image>
		</view>
		<view class="box">
			<view class="list">
				<input class="fl ipt" type="text" value="" v-model="ipt_1" placeholder="请输入注册手机号码" placeholder-style="color:#999"/>
			</view>
			<view class="list clf">
				<input ref="ipt" class="fl ipt" type="text" v-model="ipt_2" value="" placeholder="请输入6位验证码" placeholder-style="color:#999"/>
				<view class="fr right" :class="{color: ipt_1}">获取验证码</view>
			</view>
			<view class="list">
				<input class="fl ipt" type="text" v-model="ipt_3" value="" placeholder="请设置6-20位登录密码" placeholder-style="color:#999"/>
			</view>
			<view class="list">
				<input class="fl ipt" type="text" v-model="ipt_4" value="" placeholder="请再次确认登录密码" placeholder-style="color:#999"/>
			</view>
			<view class="list">
				<input class="fl ipt" type="text" value="" placeholder="推荐码(选填)" placeholder-style="color:#999"/>
			</view>
		</view>
		
		<view class="btn_r" :class="{on: ipt_1 && ipt_2 && ipt_3 && ipt_4}">注册</view>
		<navigator class="reg" url="./login">已有账号，立即登录</navigator>
		<view class="agree">注册即代表您已经同意<span>《用户服务协议》</span></view>
	</view>
</template>

<script>
	export default{
		data(){
			return{
				ipt_1: '',
				ipt_2: '',
				ipt_3: '',
				ipt_4: ''
			}
		},
		methods:{
		}
	}
</script>

<style>
	.container{
		width: 650upx;
		margin: 0 auto;
	}
	.container .user_img{
		width: 150upx;
		height: 150upx;
		background-color: #ccc;
		border-radius: 50%;
		margin: 0 auto;
	}
	.container .user_img image{
		width: 100%;
		height: 100%;
		border-radius: 50%;
	}
	
	.container .box .list{
		height: 118upx;
		font-size: 30upx;
		color: #333;
		border-bottom: 1upx solid #ddd;
	}

	.container .box .list .ipt{
		width: 400upx;
		height: 36upx;
		margin-top: 50upx;
	}
	.container .box .list .right{
		width: 200upx;
		height: 118upx;
		padding-top: 60upx;
		box-sizing: border-box;
		font-size: 26upx;
		text-align: right;
		color: #666;
	}
	.container .box .list .right.color{
		color: #fc921f;
	}

	.container .on{
		opacity: 1;
	}
	.container .reg{
		text-align: center;
		font-size: 26rpx;
		color: #666;
		margin-top: 60upx;
	}
	.container .agree{
		text-align: center;
		font-size: 22upx;
		color: #ccc;
		margin-top: 140upx;
	}
	.container .agree span{
		color: #1d93dd;
	}
</style>
