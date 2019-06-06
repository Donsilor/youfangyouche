<template>
	<view class="container">
		<view class="tit">账户可用积分</view>
		<view class="list">可用积分：<span class="color">6992</span></view>
		<view class="tit">赠送信息</view>
		<view class="list">
			<input class="ipt fl" type="text" placeholder="请输入要赠送的积分" placeholder-style="color: #999" v-model="ipt_1">
		</view>
		<view class="list line">
			<input class="ipt fl" type="text" placeholder="请输入接收人手机号" placeholder-style="color: #999" v-model="ipt_2">
		</view>
		
		<view class="btn_r" :class="{on: ipt_1 && ipt_2}">确认赠送</view>
	</view>
</template>

<script>
	export default{
		data () {
			return{
				ipt_1: '',
				ipt_2: ''
			}
		}
	}
</script>

<style>
	page{
		background-color: #f5f5f5;
	}
	.tit{
		height: 76upx;
		line-height: 86upx;
		padding-left: 20upx;
		box-sizing: border-box;
		font-size: 28upx;
		color: #999;
	}
	.list{
		height: 100upx;
		background-color: #fff;
		padding-left: 20upx;
		box-sizing: border-box;
		font-size: 30upx;
		color: #666;
		line-height: 100upx;
	}
	.line{
		border-top: 1upx solid #e5e5e5;
	}
	.list .color{
		color: #f72c2c;
	}
	.list .ipt{
		width: 80%;
		margin-top: 22upx;
	}
	
	.btn_r{
		margin-top: 125upx;
	}
</style>
