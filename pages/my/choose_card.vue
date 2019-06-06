<template>
	<view class="container">
		<view class="title">请选择提现银行卡</view>
		<view class="box">
			<view class="list" v-for="(item, index) in userItem" :key="index">
				<view class="left">
					<image src="../../static/images/bank_card_01.png"></image>
				</view>
				<view class="right">
					<view class="bank_name">{{item.bank}}</view>
					<view class="clf user">
						<view class="user_name fl">{{item.name}}</view>
						<view class="identity_card fr">
							<span>{{item.card}}</span>
							<span class="star">****</span>
							<span class="star">****</span>
							<span class="star">****</span>
							<span class="star">****</span>
						</view>
					</view>
				</view>
			</view>
		</view>
		
		<navigator class="btn" url="./add_card">添加银行卡</navigator>
	</view>
</template>

<script>
	export default{
		data () {
			return{
				userItem:[
					{
						bank:'中国银行',
						name:'赵云',
						card:'5623'
					},
					{
						bank:'广发银行',
						name:'李白',
						card:'5623'
					},
					{
						bank:'农业银行',
						name:'程咬金',
						card:'5623'
					},
					{
						bank:'工商银行',
						name:'成吉思汗',
						card:'5623'
					},
					{
						bank:'邮政银行',
						name:'张飞',
						card:'5623'
					},
					{
						bank:'中央人民银行',
						name:'孙尚香',
						card:'5623'
					},
					{
						bank:'中国银行',
						name:'赵云',
						card:'5623'
					},
					{
						bank:'广发银行',
						name:'李白',
						card:'5623'
					},
					{
						bank:'农业银行',
						name:'程咬金',
						card:'5623'
					},
					{
						bank:'工商银行',
						name:'成吉思汗',
						card:'5623'
					},
					{
						bank:'邮政银行',
						name:'张飞',
						card:'5623'
					},
					{
						bank:'中央人民银行',
						name:'孙尚香',
						card:'5623'
					}
				]
			}
		}
	}
</script>

<style>
	page{
		background-color: #f5f5f5;
	}
	.container{
		padding: 30upx 30upx 120upx;
	}
	.title{
		font-size: 28upx;
		color: #999;
	}
	.box{
		margin-top: 20upx;
	}
	.box .list{
		width: 690upx;
		padding: 20upx 30upx;
		box-sizing: border-box;
		background-color: #fff;
		margin-bottom: 20upx;
		border-radius: 20upx;
		display: flex;
		align-items: center;
	}
	.box .left{
		width: 70upx;
		height: 70upx;
		border-radius: 50%;
		margin-right: 30upx;
	}
	.box .left image{
		width: 100%;
		height: 100%;
		border-radius: 50%;
	}
	.box .right{
		width: 590upx;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
	}
	.box .right .bank_name{
		font-size: 34upx;
		color: #333;
		font-weight: bold;
		margin-bottom: 30upx;
	}
	.box .right .user{
		height: 40upx;
	}
	.box .right .user_name{
		font-size: 28upx;
		color: #666;
		width: 160upx;
		overflow: hidden;
		text-overflow: ellipsis;
		white-space: nowrap;
	}
	.box .right .identity_card{
		font-size: 28upx;
		color: #666;
		width: 360upx;
		text-align: right;
		overflow: hidden;
	}
	.box .right .identity_card span{
		float: right;
		margin-left: 10upx;
	}
	.star{
		margin-top: 6upx;
	}
	.btn{
		position: fixed;
		left: 0;
		bottom: 0;
		width: 100%;
		height: 98upx;
		background: linear-gradient(left, #ff8e06, #ff5011);
		font-size: 32upx;
		color: #fff;
		text-align: center;
		line-height: 98upx;
	}
</style>
