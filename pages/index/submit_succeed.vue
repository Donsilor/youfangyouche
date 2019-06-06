<template>
	<view class="container">
		<view class="img_box">
			<i class="iconfont iconselected"></i>
		</view>
		<view class="tit">提交成功</view>
		<view class="text">您的申请已提交成功、等待审核中...</view>
		<view class="text">预计1-2个工作日内审核完成~</view>
		<navigator class="btn_r on" open-type="switchTab" url="./index">返回首页</navigator>
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
	.img_box{
		width: 192upx;
		height: 192upx;
		margin: 192upx auto 0;
		text-align: center;
		line-height: 192upx;
	}
	.img_box i{
		font-size: 190upx;
		color: #ff8e06;
	}
	.tit{
		font-size: 34upx;
		color: #333;
		font-weight: bold;
		margin: 30upx 0;
		text-align: center;
	}
	.text{
		font-size: 28upx;
		color: #333;
		text-align: center;
	}

</style>
