<template>
	<view class="container">
		<view class="top_bgcolor">
			<view class="text">可用积分</view>
			<view class="num">68352</view>
			<view class="btn_box">
				<navigator class="btn" url="./Integral_present">赠送</navigator>
				<view class="btn">去兑换</view>
			</view>
		</view>
		
		<view class="title">
			<span class='line fl'></span>积分记录
		</view>
		
		<view class="box">
			<view class="list" v-for="(item, index) in infomationItem" :key="index">
				<view class="type">{{item.type}}</view>
				<view class="num clf">
					<view class="fl">
						订单号：<span>{{item.orderNum}}</span>
					</view>
					<view class="fr money" :class="{red:item.money>0}">{{item.money}}</view>
				</view>
				<view class="data_box">
					<span class="data">{{item.data}}</span>
					<span class="time">{{item.time}}</span>
				</view>
			</view>
		</view>
	</view>
</template>

<script>	
	export default{
		data () {
			return{
				infomationItem:[
					{
						type:'商品兑换',
						orderNum:'885645545458531',
						money:'-110',
						data:'2018-12-12',
						time:'11:11:36'
					},
					{
						type:'消费返积分',
						orderNum:'885645545458531',
						money:'+563',
						data:'2018-12-12',
						time:'11:11:36'
					},
					{
						type:'商品兑换',
						orderNum:'885645545458531',
						money:'-110',
						data:'2018-12-12',
						time:'11:11:36'
					},
					{
						type:'消费返积分',
						orderNum:'885645545458531',
						money:'+563',
						data:'2018-12-12',
						time:'11:11:36'
					},
					{
						type:'商品兑换',
						orderNum:'885645545458531',
						money:'-110',
						data:'2018-12-12',
						time:'11:11:36'
					},
					{
						type:'消费返积分',
						orderNum:'885645545458531',
						money:'+563',
						data:'2018-12-12',
						time:'11:11:36'
					},
					{
						type:'商品兑换',
						orderNum:'885645545458531',
						money:'-110',
						data:'2018-12-12',
						time:'11:11:36'
					},
					{
						type:'消费返积分',
						orderNum:'885645545458531',
						money:'+563',
						data:'2018-12-12',
						time:'11:11:36'
					}
				]
			}
		}
	}
</script>

<style>
	.top_bgcolor{
		width: 100%;
		height: 450upx;
		background: url('https://szdbi.oss-cn-shenzhen.aliyuncs.com/youfangyouche/integral_01.png') no-repeat center;
		background-size: 100% 100%;
		/* margin-top: -88upx; */
		padding-top: 160upx;
		box-sizing: border-box;
		text-align: center;
	}
	.top_bgcolor .text{
		font-size: 34upx;
		color: #fff;
		text-align: center;
	}
	.top_bgcolor .num{
		font-size: 60upx;
		color: #fff;
		margin: 10upx 0 20upx;
		text-align: center;
	}
	.btn_box{
		width: 750upx;
		padding: 0 180upx;
		display: flex;
		justify-content: space-between;
		box-sizing: border-box;
	}
	.btn{
		width: 150upx;
		height: 50upx;
		border: 1upx solid #fff;
		border-radius: 10upx;
		font-size: 30upx;
		line-height: 50upx;
		color: #fff;
	}
	
	.title{
		margin-top: 30upx;
		font-size: 34upx;
		color: #333;
		line-height: 34upx;
	}
	.title .line{
		width: 10upx;
		height: 30upx;
		background: linear-gradient(top, #ff8e06, #ff5011);
		margin: 2upx 10upx 0 20upx;
	}
	.box{
		padding: 0 20upx;
		box-sizing: border-box;
	}
	.box .list{
		padding: 30upx 0;
	}
	.box .list .type{
		font-size: 34upx;
		color: #333;
	}
	.box .list .num{
		font-size: 26upx;
		color: #888;
		margin: 16upx 0;
	}
	.box .list .num .money{
		font-size: 40upx;
		color: #fe3838;
		margin-top: -12upx;
	}
	.box .list .num .red{
		color: #0bc94e;
	}
	.box .data_box{
		font-size: 26upx;
		color: #888;
	}
	.box .data_box .data{
		margin-right: 20upx;
	}
</style>
