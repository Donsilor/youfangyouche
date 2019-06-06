<template>
	<view class="container">
		<view class="bg_img">
			<image src="../../static/images/scart_10.png"></image>
		</view>
		<view class="tit">购物车竟然是空的,快去逛逛吧~</view>
		<view class="btn">去商城逛逛</view>
		
		<view class="content">
			<view class="title">
				<i class='icon'></i>
				<view class="text">为你推荐</view>
				<i class='icon'></i>
			</view>
			<view class="box">
				<view class="list" v-for="(item, index) in shop_items" :key="index">
					<view class="img_box">
						<image src="/static/images/shoppingCart_02.png"></image>
					</view>
					<view class="text">{{item.text}}</view>
					<view class="price clf">
						<view class="fl color"><span class='small'>￥</span>{{item.price}}</view>
						<view class="fr sales_volume">销量{{item.volume}}</view>
					</view>
				</view>
			</view>
			
		</view>
	</view>
</template>

<script>
	export default{
		data(){
			return{
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
		}
		
	}
</script>

<style>
	.bg_img{
		width: 206upx;
		height: 192upx;
		margin: 60upx auto 40upx;
	}
	.bg_img image{
		width: 100%;
		height: 100%;
	}
	.tit{
		font-size: 26upx;
		color: #888;
		text-align: center;
	}
	.btn{
		width: 206upx;
		height: 60upx;
		background: linear-gradient(left bottom,#fd4d1c ,#fa1313);
		border-radius: 30upx;
		font-size: 24upx;
		color: #fff;
		text-align: center;
		line-height: 60upx;
		margin: 40upx auto;
	}
	
	.content{
		width: 100%;
		padding: 0 20upx 20upx;
		background-color: #f5f5f5;
		box-sizing: border-box;
		margin-top: 80upx;
	}
	.content .title{
		display: flex;
		justify-content: center;
		align-items: center;
		height: 80upx;
	}
	.content .icon{
		width: 34upx;
		height: 18upx;
		/* background: url(../../static/images/scart_13.png) no-repeat center; */
		/* background-size: 100% 100%; */
	}
	.content .text{
		font-size: 34upx;
		color: #666;
		font-weight: bold;
		margin: 0 20upx;
	}
	
	.content .box{
		width: 100%;
		display: flex;
		justify-content: space-between;
		flex-wrap: wrap;
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
		margin: 8upx 0 16upx;
		padding: 0 12upx;
		box-sizing: border-box;
		display: -webkit-box;
		-webkit-box-orient: vertical;
		-webkit-line-clamp: 2;
		overflow: hidden;
	}
	.content .list .price{
		padding: 0 12upx;
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
