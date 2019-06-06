<template>
	<view id="shopping_cart" class="shopping_cart">
		<view class="top">购物车
			<view class="finish" @click="compile">{{isCompile}}</view>		
		</view>
		
		<!-- 购物车有商品时显示 -->
		<view class="box" v-if="this.items != 0">
			<view class="list" v-for="(item, index) in items" :key=index>
				<view class="icon" :class="{active: item.isActive}" @click="clickOn(index)"></view>
				<view class="img_box" @click="clickOn(index)">
					<image src="/static/images/shoppingCart_01.png"></image>
				</view>
				<view class="right">
					<view class="text">{{item.text}}</view>
					<view>
						<view class="type">{{item.type}}</view>
					</view>
					<view>
						<view class="price fl">
							<span class="small">￥</span>{{item.price}}
						</view>
						<view class="quantity clf fr">
							<view class="minus fl" @click="clickMinus(index)">-</view>
							<view class="num fl">{{item.num}}</view>
							<view class="add fl" @click="clickAdd(index)">+</view>
						</view>
					</view>
				</view>		
			</view>
		</view>
		
		<view class="total clf" v-if="this.items != 0">
			<view class="fl left">
				<view class="fl all" @click="selectAll">
					<view class="icon fl" :class="{active: isAll}"></view>全选
				</view>
				<view class="fr text">
					共{{total}}件<span v-if="this.isCompile == '编辑'">,合计：<i class="color">{{allMoney}}</i></span>
				</view>
			</view>
			<view class="fr right">
				<view class="fr del" @click="ifDel">{{isSettle}}</view>
			</view>

		</view>
		
		<!-- 空车时显示 -->
		<view class="empty_cart" v-if="this.items.length == 0">
			<view class="bg_img">
				<image src="../../static/images/scart_10.png"></image>
			</view>
			<view class="tit">购物车竟然是空的,快去逛逛吧~</view>
			<navigator class="btn" open-type="switchTab" url="../shop/shop">去商城逛逛</navigator>
			
			<view class="content">
				<view class="title">
					<i class='icon'></i>
					<view class="text">为你推荐</view>
					<i class='icon'></i>
				</view>
				<view class="wrap">
					<view class="list" v-for="(item, index) in shop_items" :key="index">
						<view class="img_box">
							<image src="/static/images/shoppingCart_02.png"></image>
						</view>
						<view class="text">{{item.text}}</view>
						<view class="price">
							<view class="color"><span class='small'>￥</span>{{item.price}}</view>
							<view class="sales_volume">销量{{item.volume}}</view>
						</view>
					</view>
				</view>
				
			</view>
		</view>
		
	</view>
</template>

<script>
	export default {
		data() {
			return{
				isCompile: '编辑',
				isSettle: '结算',
				items: [
					{
						isActive: false,
						url:'',
						text: '娇兰臻彩宝石唇膏镜面口红女111111111111111111111111111滋润哑光限量版N214正品',
						type: '白云石纹壳',
						price: '150.00',
						num: '4'
					},
					{
						isActive: false,
						url:'',
						text: 'ONLY夏季新款卡通贴布宽松T恤女',
						type: '白云石纹壳',
						price: '26.00',
						num: '1'
					},
					{
						isActive: false,
						url:'',
						text: 'ONLY夏季新款小清新雪纺甜美连衣裙女',
						type: '白云石纹壳',
						price: '180.00',
						num: '2'
					},
					{
						isActive: false,
						url:'',
						text: '「王者之都」春夏新品 BURBERRY女TB 小号专属标识锁扣包80103331',
						type: '白云石纹壳',
						price: '60.00',
						num: '1'
					},
					{
						isActive: false,
						url:'',
						text: '「王者之都」春夏新品 BURBERRY女TB 小号专属标识锁扣包80103331',
						type: '白云石纹壳',
						price: '29.00',
						num: '1'
					},
					{
						isActive: false,
						url:'',
						text: '「王者之都」春夏新品 BURBERRY女TB 小号专属标识锁扣包80103331',
						type: '白云石纹壳',
						price: '299.00',
						num: '2'
					}
				],
				// 共多少件商品
				total: 0,
				// 共多少钱
				allMoney: 0,
				// 是否全选
				isAll: false,
				// 空车时推荐商品
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
		methods:{
			// 点击单个商品
			clickOn:function (i) {
				this.items[i].isActive = !this.items[i].isActive;
				if(this.items[i].isActive == true){
					this.total+=(+this.items[i].num);
					this.allPrice(i);
				}else{
					this.total-=(+this.items[i].num);
					this.allPrice(i);
				}
			},
			// 点击全部
			selectAll:function () {
				this.isAll = !this.isAll;
				if(this.isAll == true){
					this.total = 0;
					this.allMoney = 0;
					this.items.forEach(o=>{			
						o.isActive = true;
						this.total+=(+o.num);
						this.allMoney+=(+o.num*o.price);
					})
				}else{
					this.total = 0;	
					this.allMoney = 0;
					this.items.forEach(o=>{
						o.isActive = false
					})
				}
			},
			// 点击减少按钮
			clickMinus: function (e) {
				if(this.items[e].num > 1){
					this.items[e].num--;
					if(this.items[e].isActive == true){
						this.total--;
						this.allPrice(e);
					}
				}else{
					console.log('不能再少了哦')
				}
			},
			// 点击增加按钮
			clickAdd: function (e) {
				this.items[e].num++;
				if(this.items[e].isActive == true){
					this.total++;
					this.allPrice(e);
				}
			},
			// 合计价格
			allPrice: function () {
				this.allMoney = 0;
				this.items.forEach(o => {
					if(o.isActive == true){
						this.allMoney += (+o.num*o.price);
					}
				})
			},
			// 切换编辑
			compile:function () {
				this.isCompile = this.isCompile == '编辑' ? '完成' : '编辑' ;
				this.isSettle = this.isCompile == '编辑' ? '去结算' : '删除' ;
			},
			ifDel:function () {
				if(this.isCompile == '编辑'){
					uni.navigateTo({
						url: './confirm_order',
						// success: res => {},
						// fail: () => {},
						// complete: () => {}
					});
				}else{
					console.log('亲，真要忍心删除嘛？')
				}
			}
		}
	}
</script>

<style>
	.shopping_cart .top{
		position: fixed;
		left: 0;
		top: 0;
		z-index: 3;
		width: 100%;
		height: 0upx;
		overflow: hidden;
		text-align: center;
		line-height: 88upx;
		font-size: 34upx;
		color: #333;
		background: #fff;
	}
	.shopping_cart .top .finish{
		position: absolute;
		top: 6upx;
		right: 16upx;
		font-size: 26upx;
		color: #333;
	}
	.shopping_cart .box{
		padding-bottom: 90upx;
	}
	.shopping_cart .box .list{
		display: flex;
		align-items: center;
		padding: 30upx 0;
		border-bottom: 1px solid #eee;
	}
	.shopping_cart .box .list .icon,
	.shopping_cart .total .all .icon{
		width: 46upx;
		height: 46upx;
		border-radius: 50%;
		margin: 0 20upx;
		border: 1upx solid #ccc;
	}
	.shopping_cart .box .list .icon.active,
	.shopping_cart .total .all .icon.active{
		border-color: #fc921f;
		background: url('https://szdbi.oss-cn-shenzhen.aliyuncs.com/youfangyouche/icon_02.png') no-repeat center;
		background-size: 100% 100%;
	}
	.shopping_cart .box .list .img_box{
		width: 180upx;
		height: 180upx;
		background-color: saddlebrown;
	}
	.shopping_cart .box .list .img_box image{
		width: 100%;
		height: 100%;
	}
	.shopping_cart .box .list .right{
		flex: 1;
		height: 180upx;
		overflow: hidden;
		margin: 0 20upx;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
	}
	.shopping_cart .box .list .right .text{
		font-size: 26upx;
		color: #333;
		overflow: hidden;
		text-overflow:ellipsis;
		display: -webkit-box;
		-webkit-line-clamp: 2;
		-webkit-box-orient: vertical;
		width: 90%;
	}
	.shopping_cart .box .list .right .type{
		background-color: #f5f5f5;
		height: 40upx;
		padding: 0 12upx;
		border-radius: 5upx;
		line-height: 40upx;
		font-size: 24upx;
		display: inline-block;
	}
	.shopping_cart .box .list .right .price{
		color: #f70c12;
		font-size: 20upx;
	}
	.shopping_cart .box .list .right .price .small{
		font-size: 20upx;
	}
	.shopping_cart .box .list .right .quantity{
		width: 140upx;
		height: 40upx;
		border: 1upx solid #ddd;
		line-height: 38upx;
	}
	.shopping_cart .box .list .right .quantity .minus,
	.shopping_cart .box .list .right .quantity .add{
		width: 40upx;
		height: 40upx;
		text-align: center;
		color: #ddd;
	}
	.shopping_cart .box .list .right .quantity .num{
		width: 60upx;
		height: 40upx;
		border-left: 1upx solid #ddd;
		border-right: 1upx solid #ddd;
		box-sizing: border-box;
		text-align: center;
		font-size: 22upx;
		color: #999;
	}
	.shopping_cart .total{
		position: fixed;
		left: 0;
		bottom: 0;
		width: 100%;
		height: 98upx;
	}
	.shopping_cart .total .left{
		width: 73%;
		height: 100%;
		background-color: #f9f9f9;
		line-height: 98upx;
		font-size: 28upx;
		color: #888;
	}
	.shopping_cart .total .right{
		width: 27%;
		height: 100%;
	}
	.shopping_cart .total .left .icon{
		margin: 24upx 20upx 14upx 28upx;
	}
	.shopping_cart .total .left .text{
		margin-right: 20upx;
		letter-spacing: 2upx;
	}
	.shopping_cart .total .left .text .color{
		color: #ff1919;
	}
	.shopping_cart .total .del{
		width: 100%;
		height: 100%;
		background: -webkit-linear-gradient(left, #ff8e06, #ff5011);
		text-align: center;
		line-height: 98upx;
		font-size: 32upx;
		color: #fff;
	}
	
	
	/* 空车时样式 */
	.empty_cart .bg_img{
		width: 206upx;
		height: 192upx;
		margin: 60upx auto 40upx;
	}
	.empty_cart .bg_img image{
		width: 100%;
		height: 100%;
	}
	.empty_cart .tit{
		font-size: 26upx;
		color: #888;
		text-align: center;
	}
	.empty_cart .btn{
		width: 206upx;
		height: 60upx;
		background: linear-gradient(left,#ff8e06 , #ff5011);
		border-radius: 30upx;
		font-size: 24upx;
		color: #fff;
		text-align: center;
		line-height: 60upx;
		margin: 40upx auto;
	}
	
	.empty_cart .content{
		width: 100%;
		padding: 0 20upx 20upx;
		background-color: #f5f5f5;
		box-sizing: border-box;
		margin-top: 80upx;
	}
	.empty_cart .content .title{
		display: flex;
		justify-content: center;
		align-items: center;
		height: 80upx;
	}
	.empty_cart .content .icon{
		width: 34upx;
		height: 18upx;
		background: url('https://szdbi.oss-cn-shenzhen.aliyuncs.com/youfangyouche/house_03.png') no-repeat center;
		background-size: 100% 100%;
	}
	.empty_cart .content .text{
		font-size: 34upx;
		color: #666;
		font-weight: bold;
		margin: 0 20upx;
	}
	
	.empty_cart .content .wrap{
		width: 100%;
		display: flex;
		justify-content: space-between;
		flex-wrap: wrap;
	}
	.empty_cart .content .wrap .list{
		width: 344upx;
		background-color: #fff;
		margin-bottom: 20upx;
		padding-bottom: 10upx;
	}
	.empty_cart .content .wrap .list .img_box{
		width: 344upx;
		height: 344upx;
	}
	.empty_cart .content .wrap .list .img_box image{
		width: 100%;
		height: 100%;
	}
	.empty_cart .content .wrap .list .text{
		font-size: 26upx;
		color: #353535;
		margin: 8upx 0 16upx;
		padding: 0 12upx;
		box-sizing: border-box;
		display: -webkit-box;
		-webkit-box-orient: vertical;
		-webkit-line-clamp: 2;
		overflow: hidden;
		font-weight: 100;
	}
	.empty_cart .content .wrap .list .price{
		padding: 0 12upx;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
	.empty_cart .content .wrap .list .price .color{
		font-size: 32upx;
		box-sizing: border-box;
		color: #ff1919;
		font-weight: bold;
		
	}
	.empty_cart .content .wrap .list .price .color .small{
		font-size: 22upx;
	}
	.empty_cart .content .wrap .list .price .sales_volume{
		font-size: 22upx;
		color: #999;
	}
</style>

