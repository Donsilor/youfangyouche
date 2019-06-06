<template>
	<view class="container clf">
		<view class="left fl">
			<view class="list" :class="{active:changeRed == index}" v-for="(item, index) in classify_items" :key="index" @click="onChange(index)">
				<view class="sign"></view>
				{{item}}
			</view>
		</view>
		<view class="right fl">
			<navigator class="classify_r" v-for="(clothes_item, index) in clothes_items" :key = "index" url="./commodity_list">
				<view class="big_name">{{clothes_item.big_name}}</view>
				<view class="clothes_box">
					<view class="box" v-for="(clothes, index) in clothes_item.clothes_r" :key = "index">
						<view class="clothes_list">
							<image src="../../static/images/shop_08.png"></image>
						</view>
						<view class="name">{{clothes.name}}</view>
					</view>
				</view>
			</navigator>
		
		</view>
		
	</view>
</template>

<script>
	export default{
		data(){
			return{
				changeRed:0,
				classify_items:['推荐','爆品','新品','居家','鞋包','服装','电器','洗护','餐饮','文体','婴童','特色','进口','狸狸','狸狸','狸狸'],
				clothes_items:[
					{
						big_name: '男装',
						clothes_r:[
							{name: 'T恤',url: ''},
							{name: '风衣',url: ''},
							{name: '裙子',url: ''},
							{name: 'T恤',url: ''},
							{name: '风衣',url: ''},
							{name: '裙子',url: ''},
						]
					},
					{
						big_name: '女装',
						clothes_r:[
							{name: 'T恤',url: ''},
							{name: '风衣',url: ''},
							{name: '裙子',url: ''},
							{name: 'T恤',url: ''},
							{name: '风衣',url: ''},
							{name: '裙子',url: ''},
						]
					},
					{
						big_name: '童装',
						clothes_r:[
							{name: 'T恤',url: ''},
							{name: '风衣',url: ''},
							{name: '裙子',url: ''},
							{name: 'T恤',url: ''},
							{name: '风衣',url: ''},
							{name: '裙子',url: ''},
						]
					},
				]
			}
		},
		methods:{
			onChange(index){
				this.changeRed = index;
			}
		}
	}
</script>

<style>
	.title{
		position: fixed;
		top: 3.6rem;
		left: 0;
		z-index: 2;
		width: 100%;
		height: 4.4rem;
		background-color: #fff;
		text-align: center;
		line-height: 4.4rem;
		font-size: 1.7rem;
		color: #333;
		padding: 0 1rem;
		box-sizing: border-box;
	}
	.title .icon{ 
		width: 2rem;
		height: 2rem;
		margin-top: 1.1rem;
	}

	.container .left{
		position: fixed;
		left: 0;
		top: 0;
		z-index: 1;
		width: 180upx;
		height: 100%;
		padding-top: 88upx;
		background-color: #f5f5f5;
		overflow-y: scroll;
	}
	.container .left .list{
		width: 100%;
		hegiht: 90upx;
		text-align: center;
		line-height: 90upx;
		font-size: 26upx;
		color: #333;
		position: relative;
	}
	.container .sign{
		position: absolute;
		height: 30upx;
		width: 10upx;
		left: 0;
		top: 50%;
		transform: translateY(-50%);
		background-color: transparent;
	}
	.container .left .list.active{
		background-color: #fff;
	}
	.container .left .list.active .sign{
		background-color: #f70c12;
	}
	.container .right{
		position: fixed;
		left: 200upx;
		top: 0;
		z-index: 1;
		width: 550upx;
		height: 100%;
		padding: 92upx 20upx 0;
		box-sizing: border-box;
		overflow-y: scroll;
	}
	.container .right .classify_r{
		padding: 20upx 20upx 0;
		box-shadow: 0 0 3px #ccc;
		margin-bottom: 20upx;
		box-sizing: border-box;
		width: 100%;
	}
	.container .right .classify_r .big_name{
		font-size: 26upx;
		color: #333;
	}
	.container .right .classify_r .clothes_box{
		display: flex;
		justify-content: space-between;
		flex-wrap: wrap;
		margin-top: 20upx;
		
	}
	.container .right .classify_r .clothes_box .box{
		width: 150upx;
		margin-bottom: 20upx;
		font-size: 24upx;
		color: #333;
		text-align: center;
		overflow: hidden;
	}
	.container .right .classify_r .clothes_box .clothes_list{
		height: 150upx;
		width: 150upx;
		box-sizing: border-box;
		margin-bottom: 20upx;
	}
	.container .right .classify_r .clothes_box .clothes_list image{
		width: 100%;
		height: 100%;
	}
</style>
