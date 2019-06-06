<template>
	<view class="container">	
		<view class="uni-padding-wrap">
			<view class="page-section swiper">
				<view class="page-section-spacing">
					<swiper class="swiper" :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval" :duration="duration">
						<swiper-item v-for="(item, index) in url" :key="index">
							<view class="swiper-item uni-bg-red">
								<image class="swiper_img" :src="item"></image>
							</view>
						</swiper-item>
					</swiper>
				</view>
			</view>	
		</view>
		
		<view class="notice">
			<navigator class="tit" url="./message">
				<span class="fl">
					<i class='iconfont iconnotice'></i>
				</span>
				<span class='color'>通知公告</span>
				<span>春季新品现已上市！&nbsp;点击查看更多商品！</span>
			</navigator>
			<view class="box">
				<navigator class="t_list" url="./financial">
					<view class="i_box">
						<image src="../../static/images/home_icon_01.png"></image>
					</view>财商培训
				</navigator>
				<navigator class="t_list" url="./house_property">
					<view class="i_box">
						<image src="../../static/images/home_icon_02.png"></image>
					</view>房产
				</navigator>
				<navigator class="t_list">
					<view class="i_box">
						<image src="../../static/images/home_icon_03.png"></image>
					</view>购车 
				</navigator>
			</view>
		</view>
		
		<view class="member">
			<view class="img_box">
				<image src="../../static/images/home_02.png"></image>
			</view>
			<navigator class="time" url="./seckill">
				<view class="left">
					<span class='line fl'></span>限时促销
				</view>
				<view class="mid">
					<span  class='space'>距结束</span><span class='bgcolor'>13</span>：<span class='bgcolor'>54</span>：<span class='bgcolor'>26</span>
				</view> 
				<view class="right">
					<span class="fr">
						<i class='iconfont icongengduo'></i>
					</span>
					<span class="fr">全部</span>
				</view>
			</navigator>
			<view class="i_box">
				<view class="scoll">	
					<navigator class="i_list fl" v-for="(list, index) in promotionItem" :key = 'index' url="./seckill">
						<view class="img_box">
							<image src="../../static/images/home_03.png"></image>
						</view>
						<view class="now_price">￥{{list.now_price}}</view>
						<view class="odd_price">￥{{list.odd_price}}</view>
					</navigator>
				</view>
			</view>
		</view>
		
		<view class="choiceness">
			<span class="line fl"></span>精选推荐
		</view>
		
		<view class="content">
			<navigator class="list" v-for="(item, index) in shop_items" :key="index" url="../shop/commodity_list">
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
				background: ['color1', 'color2', 'color3'],
				url:[
					'../../static/images/home_01_01.png',
					'../../static/images/home_01_01.png',
					'../../static/images/home_01_01.png',
					'../../static/images/home_01_01.png',
					'../../static/images/home_01_01.png'
				],
				indicatorDots: true,
				autoplay: true,
				interval: 2000,
				duration: 500,
				
				promotionItem:[
					{url:'',now_price:'336',odd_price:'350'},
					{url:'',now_price:'336',odd_price:'350'},
					{url:'',now_price:'336',odd_price:'350'},
					{url:'',now_price:'336',odd_price:'350'},
					{url:'',now_price:'336',odd_price:'350'},
					{url:'',now_price:'336',odd_price:'350'},
				],
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
			changeIndicatorDots(e) {
				this.indicatorDots = !this.indicatorDots
			},
			changeAutoplay(e) {
				this.autoplay = !this.autoplay
			},
			intervalChange(e) {
				this.interval = e.target.value
			},
			durationChange(e) {
				this.duration = e.target.value
			}
		}
	}
</script>

<style scoped>
	.banner{
		width: 750upx;
		height: 446upx;
	}
	
	.swiper {
		width: 750upx;
		height: 446upx;
	}
	.swiper-item {
		display: block;
		width: 100%;
		height: 446upx;
		line-height: 446upx;
		text-align: center;
	}
	
	.swiper-list {
		margin-top: 40upx;
		margin-bottom: 0;
	}
	
	.uni-common-mt{
		margin-top:60upx;
		position:relative;
	}
	
	.info {
		position: absolute;
		right:20upx;
	}
	
	.swiper_img{
		width: 100%;
		height: 100%;
	}	
	
	
	.notice{
		border-top: 20upx solid #f5f5f5;
		border-bottom: 20upx solid #f5f5f5;
	}
	.notice .tit{
		width: 690upx;
		height: 70upx;
		line-height: 70upx;
		font-size: 26upx;
		margin-left: 30upx;
		border-bottom: 1upx solid #f5f5f5;
		overflow: hidden;
		text-overflow: ellipsis;
		white-space: normal;
	}
	.notice .tit i{
		color: #ff8e06;
	}
	.notice .tit .color{
		color: #ff8e06;
		margin: 0 10upx;
	}
	.notice .box{
		display: flex;
		justify-content: space-around;
		height: 230upx;
		width: 100%;
	}
	.notice .box .t_list{
		height: 100%;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		font-size: 24upx;
		color: #333;
	}
	.notice .box .t_list .i_box{
		width: 100upx;
		height: 100upx;
		margin-bottom: 20upx;
	}
	.notice .box .t_list .i_box image{
		width: 100%;
		height: 100%;
	}
	
	.member{
		border-bottom: 20upx solid #f5f5f5;
	}
	.member .img_box{
		width: 750upx;
		height: 220upx;
	}
	.member .img_box image{
		width: 100%;
		height: 100%;
	}
	
	.member .time{
		display: flex;
		justify-content: space-between;
		align-items: center;
		padding: 0 30upx;
		box-sizing: border-box;
		margin-top: 40upx;
	}
	.member .time .left{
		font-size: 34upx;
		color: #333;
		font-weight: bold;
	}
	.member .time .left .line,
	.choiceness .line{
		height: 30upx;
		width: 10upx;
		background-color: #ff8e06;
		margin: 10upx 10upx 0 0;
	}
	.member .time .mid{
		font-size: 28upx;
		color: #333;
	}
	.member .time .mid .bgcolor{
		display: inline-block;
		width: 36upx;
		height: 36upx;
		background-color: #333;
		border-radius: 5upx;
		line-height: 36upx;
		text-align: center;
		font-size: 24upx;
		color: #fff;
	}
	.member .time .mid .space{
		margin-right: 10upx;
	}
	.member .time .right{
		font-size: 28upx;
		color: #999;
	}
	.member .time .right .iconfont{
		margin: 6upx 0 0 10upx;
	}
	
	.member .i_box{
		width: 750upx;
		height: 350upx;
		padding: 30upx;
		box-sizing: border-box;
		overflow-y: hidden;
		overflow-x: scroll;
	}
	.member .scoll{
		width: 5000upx;
		padding-right: 30upx;
		/* height: 350upx; */
		/* border: 1px solid red; */
	}
	.member .i_box .i_list{
		width: 200upx;
		margin-right: 20upx;
	}
	.member .i_box .i_list .img_box{
		width: 200upx;
		height: 200upx;
	}
	.member .i_box .i_list .img_box image{
		width: 100%;
		height: 100%;
	}
	.member .i_box .i_list .now_price{
		font-size: 36upx;
		color: #f70c12;
		text-align: center;
		margin: 20upx 0 0;
	}
	.member .i_box .i_list .odd_price{
		font-size: 26upx;
		color: #999;
		text-decoration: line-through;
		text-align: center;
	}
	
	
	.choiceness{
		padding: 30upx;
		box-sizing: border-box;
		font-size: 34upx;
		color: #333;
		font-weight: bold;
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

