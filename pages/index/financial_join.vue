<template>
	<view class="container">
		<view class="order_money">
			<view class="fl left">订单金额</view>
			<view class="fr right">
				<span class='color'>￥2980</span>元
			</view>
		</view>
		<view class="type">银行转账</view>
		<view class="bgcolor">
			<view class="inform">请向公司账户进行转账，完成后请点击“通知我们”</view>
		</view>
		<view class="list">
			<view class="fl">开户名称</view>
			<view class="fr">深圳市POP/STARS有限公司</view>
		</view>
		<view class="list">
			<view class="fl">开户行</view>
			<view class="fr">中国银行深圳龙华支行</view>
		</view>
		<view class="list">
			<view class="fl">账号</view>
			<view class="fr">2523 5225 5225 2526 1244 777</view>
		</view>
		<view class="type">二维码支付</view>
		<view class="bgcolor">
			<view class="inform">请 扫码支付，完成后请点击“通知我们”</view>
		</view>
		<view class="card_box">
			<view class="img">
				<image src="../../static/images/code_03.png"></image>
			</view>
		</view>
		<view class="footer">
			<view class="hint">为了识别您的款项，请在“备注”中填写您的手机号</view>
			<view class="btn_r" @click="isShowPop = true">通知我们</view>
		</view>
		
		<!-- 弹窗 -->
		<view class="pop_up" v-if="isShowPop">
			<view class="box">
				<view class="content">
					<view class="affirm">支付确认</view>
					<view class="quiz">已完成转账支付？</view>
				</view>
				<view class="btn_box clf">
					<view class="btn fl" @click="isShowPop = false">返回</view>
					<navigator class="btn fr confirm" @click="isShowPop = false" url="./submit_succeed">确认</navigator>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default{
		data(){
			return{
				isShowPop: false
			}
		}
	}
</script>

<style>
	.container{
		background-color: #f5f5f5;
		padding: 20upx 0 130upx;
	}
	.order_money{
		width: 750upx;
		height: 100upx;
		padding: 0 30upx; 
		box-sizing: border-box;
		font-size: 32upx;
		line-height: 100upx;
		background-color: #fff;
	}
	.order_money .color{
		color: #ff1919;
		margin-right: 10upx;
	}
	.type{
		height: 82upx;
		line-height: 82upx;
		font-size: 26upx;
		color: #999;
		padding-left: 30upx;
		box-sizing: border-box;
	}
	.bgcolor{
		background-color: #fff;
	}
	.bgcolor .inform{
		width: 690upx;
		height: 106upx;
		line-height: 106upx;
		font-size: 30upx;
		margin-left: 30upx;
		box-sizing: border-box;
		background-color: #fff;
		border-bottom: 1upx solid #f5f5f5;
	}
	.list{
		height: 88upx;
		background-color: #fff;
		line-height: 88upx;
		font-size: 30upx;
		color: #333;
		padding: 0 30upx;
		box-sizing: border-box;
	}
	.list .left{
		width: 200upx;
		border: 1upx solid red;
		box-sizing: border-box;
	}
	.list .right{
		width: 500upx;
		border: 1upx solid red;
		box-sizing: border-box;
	}
	.card_box{
		width: 750;
		height: 520upx;
		padding-top: 30upx;
		background-color: #fff;
	}
	.card_box .img{
		width: 350upx;
		height: 350upx;
		margin: 0 auto;
	}
	.card_box .img image{
		width: 100%;
		height: 100%;
	}
	.hint{
		font-size: 24upx;
		color: #ff5011;
		margin: 30upx;
	}
	
	
	.pop_up{
		position: fixed;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		background: rgba(0, 0, 0, .3);
	}
	.pop_up .box{
		position: absolute;
		top: 50%;
		left: 50%;
		transform: translate(-50%, -50%);
		-webkit-transform: translate(-50%, -50%);
		width: 560upx;
		height: 290upx;
		background-color: #fff;
		border-radius: 10upx;
	}
	.pop_up .box .content{
		padding-top: 40upx;
		text-align: center;
	}
	.pop_up .box .content .affirm{
		font-size: 36upx;
		color: #000;
	}
	.pop_up .box .content .quiz{
		font-size: 30upx;
		color: #999;
		margin-top: 20upx;
	}
	.pop_up .box .btn_box{
		position: absolute;
		left: 0;
		bottom: 0;
		width: 100%;
		height: 100upx;
		border-top: 1upx solid #d2d3d5;
	}
	.pop_up .box .btn_box .btn{
		width: 50%;
		text-align: center;
		line-height: 100upx;
		font-size: 36upx;
		color: #000;
	}
	.pop_up .box .btn_box .confirm{
		color: #ff5011;
		border-left: 1upx solid #d2d3d5;
		box-sizing: border-box;
	}
</style>
