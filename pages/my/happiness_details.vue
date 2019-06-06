<template>
	<view class="container">
		<view class="box">
			<view class="list" v-for="(item, index) in infomationItem" :key="index">
				<view class="type">{{item.type}}</view>
				<view class="num clf">
					<view class="fl data_box">
						<span class="data">{{item.data}}</span>
						<span class="time">{{item.time}}</span>
					</view>
					<view class="fr money" :class="{red:item.money>0}">{{item.money}}</view>
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
						type:'提取幸福指数',
						money:'-110',
						data:'2018-12-12',
						time:'11:11:36'
					},
					{
						type:'每日增益',
						money:'+563',
						data:'2018-12-12',
						time:'11:11:36'
					},
					{
						type:'财商培训分润',
						money:'-110',
						data:'2018-12-12',
						time:'11:11:36'
					},
					{
						type:'购房分润',
						money:'+563',
						data:'2018-12-12',
						time:'11:11:36'
					},
					{
						type:'提取幸福指数',
						money:'-110',
						data:'2018-12-12',
						time:'11:11:36'
					},
					{
						type:'每日增益',
						money:'+563',
						data:'2018-12-12',
						time:'11:11:36'
					},
					{
						type:'财商培训分润',
						money:'-110',
						data:'2018-12-12',
						time:'11:11:36'
					},
					{
						type:'购房分润',
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
	.box{
		padding: 0 20upx;
		box-sizing: border-box;
	}
	.box .list{
		padding: 30upx 0;
		border-bottom: 1upx solid #ddd;
	}
	.box .list .type{
		font-size: 30upx;
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
		margin-top: -28upx;
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
