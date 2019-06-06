<template>
	<view class="container">
		<view class="box">
			<view class="list" v-for="(item, index) in infomationItem" :key="index">
				<view class="type clf">
					<view class="fl">提取幸福指数：<span>{{item.money}}</span></view>
					<view class="fr right" :class="{red: item.type == '提现失败'}">{{item.type}}</view>
				</view>
				<view class="num clf">
					<view class="fl bank">
						<span>{{item.bank}}</span>
						<span>(尾号&nbsp;{{bank_num[index]}})</span>
					</view>
					<view class="fr date">
						<span>{{item.data}}</span>
						<span>{{item.time}}</span>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default{
		data () {
			return{
				bank_num:[],
				infomationItem:[
					{
						money:'8533.00',
						type:'提现成功',
						bank: '中国银行',
						bank_num: '6228480178521564852',
						data:'2018-12-12',
						time:'11:11'
					},
					{
						money:'8533.00',
						type:'提现失败',
						bank: '中国银行',
						bank_num: '6228480178521564852',
						data:'2018-12-12',
						time:'11:11:36'
					},
					{
						money:'8533.00',
						type:'提现成功',
						bank: '中国银行',
						bank_num: '6228480178521564852',
						data:'2018-12-12',
						time:'11:11'
					},
					{
						money:'+563',
						type:'提现失败',
						bank: '中国银行',
						bank_num: '6228480178521564852',
						data:'2018-12-12',
						time:'11:11'
					},
					{
						money:'8533.00',
						type:'提现成功',
						bank: '中国银行',
						bank_num: '6228480178521568645',
						data:'2018-12-12',
						time:'11:11'
					},
					{
						money:'8533.00',
						type:'提现失败',
						bank: '中国银行',
						bank_num: '6228480178521562453',
						data:'2018-12-12',
						time:'11:11'
					},
					{
						money:'8533.00',
						type:'提现成功',
						bank: '中国银行',
						bank_num: '6228480178521561538',
						data:'2018-12-12',
						time:'11:11'
					},
					{
						money:'8533.00',
						type:'提现失败',
						bank: '中国银行',
						bank_num: '6228480178521564852',
						data:'2018-12-12',
						time:'11:11'
					}
				]
			}
		},
		methods:{
			tail() {
				if(this.infomationItem){
					this.infomationItem.forEach(o => {
						this.bank_num.push(o.bank_num.slice(-4))
					})
				}
			}
		},
		mounted() {
			this.tail()
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
		color: #535353;
	}
	.box .list .type .right{
		color: #04b521;
	}
	.box .list .type .red{
		color: #fe3434;
	}
	.box .list .num{
		font-size: 26upx;
		color: #888;
		margin: 16upx 0;
	}
	.box .list .num .bank span{
		margin-right: 10upx;
	}
	.box .list .num .date span{
		margin-left: 20upx;
	}
</style>
