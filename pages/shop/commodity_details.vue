<template>
	<view class="container">
		<view class="banner">
			<image src="../../static/images/shop_details_01.png"></image>
		</view>
		
		<view class="content">
			<view class="tit">芭比娃娃Barbie&puma联合款娃娃女孩公主玩具黑标珍藏款新品</view>
			<view class="price">¥459</view>
			<view class="expressage clf">
				<view class = 'fl'>快递<span>10.00</span></view>
				<view class = 'fr'>销量<span>1268</span></view>
			</view>
		</view>
		
		<view class="specification clf" @click="isShowPop = true">
			<view class="fl spec_r">选择</view>
			<view class="fl">请选择规格</view>
			<view class="fr icon">
				<i class="iconfont icongengduo"></i>
			</view>		
		</view>
		
		<view class="title">商品详情</view>
		<view class="commodity_particulars">
			<image src="../../static/images/shop_details_03.png"></image>
		</view>
		
		<view class="footer_r clf">
			<view class="list left">
				<view>
					<view class="i_box">
						<view class="icon">
							<i class="iconfont iconshoucang"></i>
						</view>
						<view class="text">收藏</view>
					</view>
				</view>
				<navigator open-type="switchTab" url="../shopping_cart/shopping_cart">
					<view class="i_box">
						<view class="icon">
							<i class="iconfont iconcart"></i>
						</view>
						<view class="text">购物车</view>
					</view>
				</navigator>
			</view>
			<navigator open-type="switchTab" url="../shopping_cart/shopping_cart">
				<view class="list mid">加入购物车</view>
			</navigator>
			<view class="list right">立即购买</view>
		</view>
		
		
		<!-- 选择规格弹窗 -->
		<view class="pop_up">
			<view class="layer" v-if="isShowPop"></view>
			
			<transition name="slide">
				<view class="wrap" v-if="isShowPop">			
					<view class="box">
						<view class="top">
							<view class="top_l">
								<view class="img_box">
									<image src="../../static/images/shoppingCart_04.png"></image>
								</view>
								<view class="text">
									<view class="price">¥459.00</view>
									<view class="type">已选：粉色/黑标珍藏版</view>
								</view>
							</view>
							<view class="top_r" @click="isShowPop = false">
								<i class="iconfont iconshanchu"></i>
							</view>
						</view>
						
						<view class="classify">
							<view class="c_tit">颜色分类</view>
							<view class="c_box clf">
								<view class="list fl" :class="{on:changeRed == 1}" @click="onChangeT(1)">白色</view>
								<view class="list fl" :class="{on:changeRed == 2}" @click="onChangeT(2)">粉色</view>
							</view>
						</view>
						<view class="classify">
							<view class="c_tit">型号分类</view>
							<view class="c_box clf">
								<view class="list fl" :class="{on:changeRed1 == 3}" @click="onChangeR(3)">普通</view>
								<view class="list fl" :class="{on:changeRed1 == 4}" @click="onChangeR(4)">限量水袖版</view>
							</view>
						</view>
						
						<view class="btn_box clf">
							<navigator class="fl btn left" open-type="switchTab" url="../shopping_cart/shopping_cart">加入购物车</navigator>
							<view class="fr btn right">立即购买</view>
						</view>
					</view>
				</view>
			</transition>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				isShowPop: false,
				changeRed: "1",
				changeRed1: "3" 
			}
		},
		methods:{
			onChangeT(e){
				this.changeRed = e;
			},
			onChangeR(k){
				this.changeRed1 = k;
			}
		},
		mounted() {
			window.addEventListener('scroll', this.appScroll)
		}
	}
</script>

<style>
	.header{
		position: fixed;
		top: 0;
		left: 0;
		z-index: 20;
		width: 100%;
		height: 80upx;
		background-color: rgba(255, 255, 255, 0);
		color: #fff;
	}
	
	.header .left{
		position: absolute;
		left: 20upx;
		top: 10upx;
		width: 60upx;
		height: 60upx;
		text-align: left;
		line-height: 60upx;
		background-color: rgba(0, 0, 0, .3);
		color: rgba(255, 255, 255, 1);
		text-align: center;
		line-height: 56upx;
		border-radius: 50%;
	}
	.header .left .iconfont{
		font-size: 32upx;
	}
	.header .right{
		position: absolute;
		right: 20upx;
		top: 10upx;
		width: 60upx;
		height: 60upx;
		background-color: rgba(0, 0, 0, .3);
		color: rgba(255, 255, 255, 1);
		text-align: center;
		line-height: 56upx;
		border-radius: 50%;
	}
	.header .right .iconfont{
		font-size: 32upx;
	}
	.header .right .btn{
		position: absolute;
		top: 0;
		left: 0;
		z-index: 2;
		width: 100%;
		height: 100%;
		background-color: transparent;
	}
	.header .title{
		font-size: 34upx;
		text-align: center;
		line-height: 80upx;
	}
	
	.banner{
		width: 750upx;
		height: 750upx;
		/* position: relative; */
	}
	.banner .top{
		position: absolute;
		z-index: 2;
		top: 0;
		left: 0;
		width: 100%;
		padding: 0 20upx;
		box-sizing: border-box;
		border: 1px solid red;
	}
	.banner .top .icon{
		width: 60upx;
		height: 60upx;
		border-radius: 50%;
		background-color: rgba(0,0,0,.3);
	}
	.banner image{
		width: 100%;
		height: 100%;
	}
	
	.content{
		width: 100%;
		padding: 0 20upx 20upx;
		box-sizing: border-box;
	}
	.content .tit{
		font-size: 30upx;
		color: #333;
		font-weight: bold;
		margin-top: 10upx;
	}
	.content .price{
		font-size: 48upx;
		color: #ff1919;
		margin: 20upx 0;
	}
	.content .expressage{
		font-size: 28upx;
		color: #888;
	}
	.content .expressage span{
		margin-left: 12upx;
	}
	
	.specification{
		width: 100%;
		height: 100upx;
		line-height: 100upx;
		border-style: solid;
		border-width: 20upx 0;
		border-color: #f0f0f0;
		padding: 0 30upx;
		font-size: 30upx;
		color: #333;
	}
	.specification .spec_r{
		color: #888;
		margin-right: 20upx;
	}
	.specification .icon{
		height: 44upx;
		width: 44upx;
		margin: 30upx 50upx 0 0;
		line-height: 44upx;
		color: #ccc;
	}
	.title{
		font-size: 32upx;
		color: #000;
		text-align: center;
		line-height: 90upx;
		font-weight: bold;
	}
	.commodity_particulars{
		width: 100%;
		height: 1080upx;
		/* line-height: 4.5rem; */
	}
	.commodity_particulars image{
		width: 100%;
		height: 100%;
	}
	
	.footer_r{
		position: fixed;
		left: 0;
		bottom: 0;
		z-index: 2;
		width: 100%;
		height: 98upx;
		background-color: #fff;
	}
	.footer_r .list{
		float: left;
		width: 33.33%;
		text-align: center;
		line-height: 98upx;
		font-size: 32upx;
		color: #fff;
	}
	.footer_r .mid{
		background: linear-gradient(left, #ffc90b, #ff960f);
	}
	.footer_r .right{
		background: linear-gradient(left, #ff7603, #ff4913);
	}
	.footer_r .left{
		display: flex;
		justify-content: space-between;
		padding: 10upx 40upx;
		box-sizing: border-box;
		line-height: 0;
		height: 98upx;
		color: #333;
		font-size: 20upx;
	}
	.footer_r .i_box{
		text-align: center;		
	}
	.footer_r .left .icon{
		width: 44upx;
		height: 44upx;
		margin: 0 auto 18upx;
		text-align: center;
		line-height: 44upx;
	}
	.footer_r .left .icon i{
		font-size: 40upx;
	}
	
	/* 弹窗样式 */
	.layer{
		position: fixed;
		left: 0;
		top: 0;
		z-index: 6;
		width: 100%;
		height: 100%;
		background-color: rgba(0,0,0,.3);
	}
	.wrap{
		position: fixed;
		left: 0;
		top: 0;
		z-index: 6;
		width: 100%;
		height: 100%;
	}
	.box{
		position: absolute;
		left: 0;
		width: 100%;
		bottom: 0;
		/* height: 0; */
		padding: 30upx 20upx 40upx;
		box-sizing: border-box;
		background-color: #fff;
	}
	
	.slide-enter-active {
    animation-name: slideInUp;
    animation-duration: 0.8s;
    animation-fill-mode: both;
	}
	
	.slide-leave-active {
		animation-name: slideOutDown;
		animation-duration: .8s;
		animation-fill-mode: both;
	}
	
	@keyframes slideInUp {
		0% {
			transform: translate3d(0, 100%, 0);
			visibility: visible;
		}
		
		to {
			transform: translateZ(0);
		}
	}
	
	@keyframes slideOutDown {
		0% {
			transform: translateZ(0);
		}

		to {
			visibility: hidden;
			transform: translate3d(0, 100%, 0);
		}
	}
	
	.delay-leave-active {
		-webkit-animation-delay: 0.2s;
		-moz-animation-delay: 0.2s;
		-o-animation-delay: 0.2s;
		animation-delay: 0.2s;
	}

	
	
	.wrap .timer{
		transition: height 20s;
		height: auto;
	}
	.wrap .top{
		display: flex;
		position: relative;
	}
	.wrap .top .top_l{
		display: flex;
		flex: 1;
	}
	.wrap .top_l .img_box{
		width: 160upx;
		height: 160upx;
		border-radius: 10upx;
	}
	.wrap .top_l .img_box image{
		width: 100%;
		height: 100%;
	}
	.wrap .top_l .text{
		flex: 1;
		height: 160upx;
		padding-top: 70upx;
		box-sizing: border-box;
		margin: 0 60upx 0 20upx;
	}
	.wrap .top_l .price{
		font-size: 34upx;
		color: #ff1919;
		margin-bottom: 20upx;
	}
	.wrap .top_l .type{
		font-size: 24upx;
		color: #333;
		overflow: hidden;
		text-overflow: ellipsis;
		white-space: nowrap;
	}
	.wrap .top .top_r{
		position: absolute;
		width: 50upx;
		height: 50upx;
		top: 0;
		right: 0;
		line-height: 50upx;
		text-align: center;
	}
	.wrap .top .top_r .iconshanchu{
		font-size: 46upx;
		color: #bbb;
	}
	
	.wrap .classify{
		margin-top: 60upx;
	}
	.wrap .classify .c_tit{
		font-size: 28upx;
		color: #333;
		margin-bottom: 40upx;
	}
	.wrap .classify .list{
		height: 46upx;
		padding: 0 20upx;
		border-radius: 5upx;
		background-color: #efefef;
		line-height: 42upx;
		text-align: center;
		font-size: 26upx;
		color: #333;
		margin-right: 40upx;
		border: 1px solid #efefef;
	}
	.wrap .classify .on{
		background-color: #ffeeee;
		color: #f70c12;
		border: 1px solid #f70c12;
		box-sizing: border-box;
	}
	.wrap .btn_box{
		width: 100%;
		height: 80upx;
		padding: 0 80upx;
		box-sizing: border-box;
		margin-top: 120upx;
	}
	.wrap .btn_box .btn{
		width: 50%;
		height: 80upx;
		line-height: 80upx;
		text-align:  center;
		font-size: 28upx;
		color: #fff;
	}
	.wrap .btn_box .left{
		background: linear-gradient(left, #fbbc15, #ffa51c);
		border-radius: 40upx 0 0 40upx;
	}
	.wrap .btn_box .right{
		background: linear-gradient(left, #fa1313, #fd4d1c);
		border-radius: 0 40upx 40upx 0;
	}
</style>
