<template>
	<view class="container">
		<view class="filter clf">
			<view class="list fl" :class="{active:changeRed==0}" @click="clickOn(0)">默认排序</view>
			<view class="list fl" :class="{active:changeRed==1}" @click="clickOn(1)">新品</view>
			<view class="list fl" :class="{active:changeRed==2}" @click="clickOn(2)">销量</view>
			<view class="list fl" :class="{active:changeRed==3}" @click="clickOn(3)">
				<view class="inline">价格</view>
				<view class="inline line_box">
					<view class="triangle1" :class="{on:rankOn == 1}" @click="rank(1)"></view>
					<view class="triangle2" :class="{on:rankOn == 2}" @click="rank(2)"></view>
				</view>
			</view>
		</view>

		<view class="content">
			<navigator class="list" v-for="(item, index) in shop_items" :key="index" url="./commodity_details">
				<view class="img_box">
					<image src="/static/images/shoppingCart_02.png"></image>
				</view>
				<view class="text">{{item.text}}</view>
				<view class="price clf">
					<view class="fl color"><span class='small'>￥</span>{{item.price}}</view>
					<view class="fr sales_volume">销量{{item.volume}}</view>
				</view>
			</navigator>
			
		</view>

	</view>
</template>

<script>
	export default {
		data() {
			return {
				changeRed:'',
				rankOn: '1',
				shop_items:[
					{
						url:'',
						text:'Five Plus2019新款女夏装短袖T恤女棉质刺绣图案体...',
						price:'299.00',
						volume:'2235'
					},
					{
						url:'',
						text:'ONLY2019夏季新款迪士尼小飞象宽松女T恤',
						price:'299.00',
						volume:'2235'
					},
					{
						url:'',
						text:'Five Plus2019新款女夏装短袖T恤女棉质刺绣图案体...',
						price:'299.00',
						volume:'2235'
					},
					{
						url:'',
						text:'ONLY2019夏季新款迪士尼小飞象宽松女T恤',
						price:'299.00',
						volume:'2235'
					},
					{
						url:'',
						text:'Five Plus2019新款女夏装短袖T恤女棉质刺绣图案体...',
						price:'299.00',
						volume:'2235'
					},
					{
						url:'',
						text:'ONLY2019夏季新款迪士尼小飞象宽松女T恤',
						price:'299.00',
						volume:'2235'
					},
					{
						url:'',
						text:'Five Plus2019新款女夏装短袖T恤女棉质刺绣图案体...',
						price:'299.00',
						volume:'2235'
					},
					{
						url:'',
						text:'ONLY2019夏季新款迪士尼小飞象宽松女T恤',
						price:'299.00',
						volume:'2235'
					}
				]
			}
		},
		methods: {
			clickOn(e){
				this.changeRed = e;
			},
			rank(e){
				this.rankOn = e;
			}
		}
	}
</script>

<style>
	page{
		background-color: #f5f5f5;
	}
	.filter{
		position: fixed;
		top: 0;
		left: 0;
		z-index: 3;
		width: 100%;
		height: 80upx;
		background-color: #fff;
		line-height: 80upx;
	}
	.filter .list{
		width: 25%;
		height: 100%;
		text-align: center;
		font-size: 26upx;
		color: #333;
		box-sizing: border-box;
	}
	.filter .list.active{
		color: #fc921f;
	}
	.filter .list .inline{
		display: inline-block;
		text-align: center;
	}
	.filter .line_box{
		margin: 0 0 -2upx 8upx;
	}
	.filter .triangle1{
		width: 0;
		height: 0;
		border-style: solid;
		border-width: 0 7upx 10upx 7upx;
		border-color: transparent transparent #000 transparent;	
		margin-bottom: 4upx;
	}
	.filter .triangle2{
		width: 0;
		height: 0;
		border-style: solid;
		border-width: 10upx 7upx 0 7upx;
		border-color: #000 transparent transparent transparent;	
	}
	.filter .triangle1.on{
		border-color: transparent transparent #fc921f transparent;	
	}
	.filter .triangle2.on{
		border-color: #fc921f transparent transparent transparent;
	}
	
	.content{
		width: 100%;
		display: flex;
		justify-content: space-between;
		flex-wrap: wrap;
		padding: 20upx 20upx 40upx;
		box-sizing: border-box;
		background-color: #f5f5f5;
	}
	.content .list{
		width: 344upx;
		background-color: #fff;
		margin-bottom: 20upx;
		padding-bottom: 10upx;
	}
	.content .list .img_box{
		width: 344upx;
		height: 344upx;
	}
	.content .list .img_box image{
		width: 100%;
		height: 100%;
	}
	.content .list .text{
		font-size: 26upx;
		color: #353535;
		margin: 20upx 0 16upx;
		padding: 0 20upx;
		box-sizing: border-box;
		display: -webkit-box;
		-webkit-box-orient: vertical;
		-webkit-line-clamp: 2;
		overflow: hidden;
	}
	.content .list .price{
		padding: 0 20upx;
	}
	.content .list .price .color{
		font-size: 32upx;
		box-sizing: border-box;
		color: #ff1919;
	}
	.content .list .price .color .small{
		font-size: 22upx;
	}
	.content .list .price .sales_volume{
		font-size: 22upx;
		color: #999;
	}
	

</style>
