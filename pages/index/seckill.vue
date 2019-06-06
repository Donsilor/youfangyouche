<template>
	<view class="container">
		<view class="banner">
			<image src="../../static/images/09_02.png"></image>
		</view>
		<view class="activity">
			<view class="scroll" ref="scro" :style="{width:sWidth,left:sLeft}">
				<view class="list fl" v-for="(item, index) in activityItem" :key = "index" :class="{on: isUnderway == index}" @click="activity(index)">
					<view class="square">
						<view class="time">{{item.time}}</view>
						<view class="status">{{item.status}}</view>
					</view>
					<view class="triangle"></view>
				</view>
			</view>
		</view>
		
		<view class="line_box">
			<view class="content">本场还剩
				<span>11:17:52</span>
			</view>
		</view>
		
		<view class="box">
			<navigator class="list" v-for="(item, index) in shopItem" :key = "index" url="../shop/commodity_details">
				<view class="fl img_box">
					<image src="../../static/images/shoppingCart_01.png"></image>
				</view>
				<view class="fr right">
					<view class="name">{{item.name}}</view>
					<view class="price">
						<span class="bgcolor">秒杀价</span>
						<span class="now_price"><i class="small">￥</i>{{item.now_price}}</span>
						<span class="odd_price">{{item.odd_price}}</span>
					</view>
				</view>
			</navigator>
		</view>
	</view>
</template>

<script>
	export default{
		data () {
			return{
				// 更改数据字段一定同js中一起更改!!
				// 更改数据字段一定同js中一起更改!!
				activityItem:[
					{time:'16:00',status:'已开抢'},
					{time:'20：00',status:'已开抢'},
					{time:'22：00',status:'抢购中'},
					{time:'明日12：00',status:'即将开始'},
					{time:'明日12：00',status:'即将开始'},
					{time:'明日12：00',status:'即将开始'}
				],
				// 正在进行的哪个
				isUnderway: 2,
				sWidth: '750upx',
				sLeft: '0',
				shopItem:[
					{
						name:'娇兰臻彩宝石唇膏镜面口红女滋润哑光限量版N214正品',
						now_price:'499.00',
						odd_price:'699.00'
					},
					{
						name:'ONLY夏季新款卡通贴布宽松T恤女',
						now_price:'499.00',
						odd_price:'699.00'
					},
					{
						name:'ONLY夏季新款小清新雪纺甜美连衣裙女',
						now_price:'499.00',
						odd_price:'699.00'
					},
					{
						name:'「王者之都」春夏新品 BURBERRY女TB 小号专属标识锁扣包80103331',
						now_price:'499.00',
						odd_price:'699.00'
					}
				]
				
			}
		},
		methods: {
			activity(e) {
				var old = this.isUnderway;
				this.isUnderway = e;
				
				if(this.isUnderway >= 2 && this.isUnderway > old){
					var _this = this;
					
					var timer = setInterval(function () {
						// console.log(_this.sLeft)
						_this.sLeft = parseInt(_this.sLeft) - 15;
						_this.sLeft = _this.sLeft+'upx';
				
						if(parseInt(_this.sLeft) <= ((_this.isUnderway+1)*190-375-95)*-1){
							_this.sLeft = ((_this.isUnderway+1)*190-375-95)*-1 + 'upx';
							clearInterval(timer);
						}
					},20)
				}
				if(this.isUnderway >= 2 && this.isUnderway < old){
					var _this = this;
					
					var timer = setInterval(function () {
						// console.log(_this.sLeft)
						_this.sLeft = parseInt(_this.sLeft) + 15;
						_this.sLeft = _this.sLeft+'upx';
				
						if(parseInt(_this.sLeft) >= ((_this.isUnderway+1)*190-375-95)*-1){
							_this.sLeft = ((_this.isUnderway+1)*190-375-95)*-1+'upx';
							clearInterval(timer);
						}
					},20)
				}
				if(this.isUnderway < 2){
					var _this = this;
					
					var timer = setInterval(function () {
						// console.log(_this.sLeft)
						_this.sLeft = parseInt(_this.sLeft) + 15;
						_this.sLeft = _this.sLeft+'upx';
									
						if(parseInt(_this.sLeft) >= 0){
							_this.sLeft = 0;
							clearInterval(timer);
						}
					},20)
				}
				
							// console.log(this.isUnderway);
			},
			scrollWidth(){
				if(this.activityItem.length > 2){
					this.sWidth = this.activityItem.length*190+'upx'
				}
				if(this.isUnderway>1){
					this.sLeft = ((this.isUnderway+1)*190-375-95)*-1 + 'upx';
				}
			}
		},
		mounted () {
			this.scrollWidth()
		}
	}
</script>

<style>
	.banner{
		width: 750upx;
		height: 252upx;
	}
	.banner image{
		width: 100%;
		height: 100%;
	}
	.activity{
		width: 100%;
		height: 116upx;
		overflow: scroll;
		position: relative;
	}
	.activity .scroll{
		width: 5000upx;
		height: 116upx;
		position: absolute;
		left: 0;
		top: 0;
	}
	.activity .list{
		width: 190upx;
		height: 116upx;
		position: relative;
	}
	.activity .list .square{
		width: 190upx;
		height: 100upx;
		background-color: #fc921f;
		font-size: 26upx;
		color: #666;
		padding-top: 12upx;
		box-sizing: border-box;
		text-align: center;
		line-height: 36upx;
		opacity: .6;
	}
	.activity .list .triangle{
		position: absolute;
		top: 100upx;
		left: 50%;
		transform: translateX(-50%);
		-webkit-transform: translateX(-50%);
		width: 0;
		height: 0;
		border-style: solid;
		border-color: transparent;
		border-width: 16upx 12upx 0 12upx;
	}
	.activity .on .square{
		opacity: 1;
	}
	.activity .on .triangle{
		border-color: #fc921f transparent transparent transparent;
	}
	.line_box{
		position: relative;
		width: 690upx;
		border-top: 3upx solid #e7e7e7;
		margin: 50upx 30upx;
	}
	.line_box .content{
		position: absolute;
		top: -20upx;
		left: 50%;
		transform: translateX(-50%);
		-webkit-transform: translateX(-50%);
		font-size: 30upx;
		line-height: 32upx;
		padding: 0 20upx;
		background-color: #fff;
		font-weight: normal;
	}
	.line_box .content span{
		margin-left: 10upx;
	}
	.box{}
	.box .list{
		display: flex;
		align-items: center;
		margin-bottom: 60upx;
		padding: 0 20upx;
	}
	.box .list .img_box{
		width: 180upx;
		height: 180upx;
		margin-right: 20upx;
	}
	.box .list .img_box image{
		width: 100%;
		height: 100%;
	}
	.box .list .right{
		height: 180upx;
		flex: 1;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
	}
	.box .list .right .name{
		font-size: 26upx;
		color: #333;
		display: -webkit-box;
		-webkit-box-orient: vertical;
		-webkit-line-clamp: 2;
		overflow: hidden;
	}
	.box .list .right .price{
		display: flex;
		align-items: center;
	}
	.box .list .right .bgcolor{
		height: 32upx;
		padding: 0 8upx;
		background-color: #fa6c6c;
		border-radius: 5upx;
		font-size: 24upx;
		color: #fff;
		line-height: 32upx;
	}
	.box .list .right .now_price{
		font-size: 30upx;
		color: #f70c12;
	}
	.box .list .right .now_price .small{
		font-size: 20upx;
	}
	.box .list .right .odd_price{
		font-size: 26upx;
		text-decoration: line-through;
		color: #666;
	}
	.box .list .right span{
		margin-right: 20upx;
	}
</style>
