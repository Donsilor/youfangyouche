<template>
	<view class="container">
		<view class="user_img">
			<image src="../../static/images/user.png"></image>
		</view>
		<view class="box">
			<view class="list">
				<input class="fl ipt" type="text" value="" :placeholder="ipt_1" placeholder-style="color:#999" v-model="ipt1"/>
			</view>
			<view class="list clf">
				<input ref="ipt" class="fl ipt" :type="text" value="" :placeholder="ipt_2" placeholder-style="color:#999" v-model="ipt2"/>
				<view class="fr clf right">
					<span class="fl iconfont" v-if="ifShow" :class="[{iconmimabukejian: isLook == false},{iconmimakejian: isLook == true}]" @click = "look()"></span>
					<view class="fr forget" :class="[{verification: ifShow == false},{color: this.ipt1 && ifShow == false}]" url="./find_password" @click="findPassword">{{forget}}</view>
				</view>
			</view>
		</view>
		
		<navigator open-type="switchTab" url="./index" class="btn" :class="{on: ipt1 && ipt2}">登录</navigator>
		<view class="reg clf">
			<view class="fl" @click="chooseWay">{{loginWay}}</view>
			<navigator class="fr" url="./reg">新用户注册</navigator>
		</view>
	</view>
</template>

<script>
	export default{
		data(){
			return{
				isLook: false,
				ifShow: true,
				ipt1: '',
				ipt2: '',
				text: 'password',
				ipt_1:'请输入ID/手机号',
				ipt_2:'请输入登录密码',
				forget: '忘记密码',
				loginWay:'短信验证码登录'
			}
		},
		methods:{
			look(){
				this.isLook = !this.isLook;
				this.text = this.text == 'password' ? 'text' : 'password';
			},
			chooseWay(){
				if(this.loginWay == '短信验证码登录' ){
					this.ipt_1 = '请输入手机号';
					this.ipt_2 = '请输入6位验证码';
					this.ipt1 = '';
					this.ipt2 = '';
					this.loginWay = '密码登录';	
					this.forget = '获取验证码';
					this.ifShow = false;
				}else{
					this.ipt_1 = '请输入ID/手机号';
					this.ipt_2 = '请输入登录密码';
					this.ipt1 = '';
					this.ipt2 = '';
					this.loginWay = '短信验证码登录';	
					this.forget = '忘记密码';
					this.ifShow = true;
				}
			},
			findPassword(){
				if(this.forget == '忘记密码'){
					uni.navigateTo({
						url: './find_password'
					})
				}
			}
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
	
	.container .box{
	}
	.container .box .list{
		height: 118upx;
		border-bottom: 1upx solid #ddd;
		font-size: 30upx;
		color: #333;
	}
	
	.container .box .list .ipt{
		width: 400upx;
		height: 36upx;
		margin-top: 50upx;
		font-size: 30upx;
		border: 0;
		outline: none;
	}
	.container .box .list .right{
		width: 200upx;
		height: 118upx;
		padding-top: 60upx;
		box-sizing: border-box;
	}
	.container .box .list .right .iconfont{
		padding: 0 22upx 6upx 0;
		border-right: 1upx solid #ddd;
	}
	.container .box .list .right .forget{
		height: 40upx;
		line-height: 36upx;
		font-size: 26upx;
		color: #666;
	}
	.container .box .list .right .verification{
		color: #999;
	}
	.container .box .list .right .color{
		color: #fc921f;
	}
	.container .btn{
		width: 650upx;
		height: 94upx;
		background: linear-gradient(left, #ff8e06, #ff5011);
		border-radius: 47upx;
		font-size: 28upx;
		color: #fff;
		line-height: 94upx;
		text-align: center;
		margin: 90upx auto 60upx;
		opacity: .5;
	}
	.container .on{
		opacity: 1;
	}
	.container .reg{
		font-size: 26upx;
		color: #666;
	}
</style>
