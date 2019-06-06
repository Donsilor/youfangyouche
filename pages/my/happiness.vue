<template>
	<view class="container">	
		<view class="top_bgcolor">
			<view class="allow">可提取幸福指数</view>
			<view class="show clf">
				<view class="fl num">{{happinessItem.allow}}</view>
				<navigator class="fr btn" url="./choose_card">提现</navigator>
			</view>
			<view class="already">已获得幸福指数{{happinessItem.already}}</view>
			<view class="box clf">
				<view class="left fl">
					<view class="earnings">昨日收益（元）</view>
					<view class="earnings_num">{{happinessItem.today}}</view>
				</view>
				<view class="right fl">
					<view class="earnings">累计收益（元）</view>
					<view class="earnings_num">{{happinessItem.all}}</view>
				</view>
			</view>
		</view>
		<view class="content">
			<navigator class="list" url="./happiness_details">
				<view class="fl">幸福指数明细</view>
				<i class="fr iconfont icongengduo"></i>
			</navigator>
			<navigator class="list" url="./choose_card">
				<view class="fl">银行卡</view>
				<i class="fr iconfont icongengduo"></i>
			</navigator>
			<navigator class="list" url="withdraw_log">
				<view class="fl">提现记录</view>
				<i class="fr iconfont icongengduo"></i>
			</navigator>
		</view>
	</view>
</template>

<script>
	export default{
		data () {
			return{
				back:'',
				title: '',
				subhead: '',	
				happinessItem:{
					allow:'18352.00',
					already:'89852.00',
					today:'326.00',
					all:'523.00'
				},
			}
		}
	}
</script>

<style>
	.top_bgcolor{
		width: 100%;
		height: 538upx;
		background: url('https://szdbi.oss-cn-shenzhen.aliyuncs.com/youfangyouche/hippiness_01.png') no-repeat center;
		background-size: 100% 100%;
		padding: 0 20upx;
		box-sizing: border-box;
		padding-top: 120upx;
		box-sizing: border-box;
	}
	.top_bgcolor .allow{
		font-size: 26upx;
		color: #f9dad0;
	}
	.top_bgcolor .show{
		margin: 10upx 0;
	}
	.top_bgcolor .show .num{
		font-size: 80upx;
		color: #fff;
	}
	.top_bgcolor .show .btn{
		width: 100upx;
		height: 50upx;
		border: 1upx solid #fff;
		border-radius: 10upx;
		text-align: center;
		line-height: 48upx;
		font-size: 30upx;
		color: #fff;
		margin-top: 24upx;
	}
	.already{
		font-size: 30upx;
		color: #fff;
	}
	.box{
		width: 100%;
		margin-top: 60upx;
	}
	.box .fl{
		width: 50%;
	}
	.box .earnings{
		font-size: 26upx;
		color: #f9dad0;
	}
	.box .earnings_num{
		font-size: 56upx;
		color: #fff;
		margin-top: 10upx;
	}
	
	.content{
		width: 100%;
		padding: 0 20upx;
		box-sizing: border-box;
		border-top: 20upx solid #f5f5f5;
	}
	.content .list{
		height: 172upx;
		line-height: 172upx;
		font-size: 36upx;
		color: #343434;
	}
	.content .list:not(:last-child){
		border-bottom: 2upx solid #f2f2f2;
	}
	.content i{
		width: 40upx;
		height: 40upx;
		text-align: center;
		line-height: 40upx;
		margin-top: 66upx;
	}
</style>
