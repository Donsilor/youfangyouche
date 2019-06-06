<template>
	<view>
		<!-- <view class="footer">
			<view class="list" v-for="(list, index) in f_list" :key = index @click = 'toPath(index)'>
				<view class="f_icon" :class="[list.classR,{active:index_r == index}]"></view>
				<view class="f_text">{{list.text}}</view>
			</view>
		</view> -->
		
		<view class="footer">
			<navigator url="../index/index" class="navs">
				<view class="list" @click = 'toPath(0)'>
					<view class="f_icon homepage" :class="{active:this.index_r==0}"></view>
					<view class="f_text">首页</view>
				</view>
			</navigator>
			
			<navigator url="../shop/shop" class="navs">
				<view class="list" @click = 'toPath(1)'>
					<view class="f_icon stock_right" :class="{active:this.index_r==1}"></view>
					<view class="f_text">商城</view>
				</view>
			</navigator>
			
			<navigator url="../shopping_cart/shopping_cart" class="navs">
				<view class="list" @click = 'toPath(2)'>
					<view class="f_icon shopping_cart" :class="{active:this.index_r==2}"></view>
					<view class="f_text">购物车</view>
				</view>
			</navigator>
			
			<navigator url="../my/my" class="navs">
				<view class="list" @click = 'toPath(3)'>
					<view class="f_icon my" :class="{active:this.index_r==3}"></view>
					<view class="f_text">我的</view>
				</view>
			</navigator>

		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				// 默认点击状态
				index_r: 0
				
				// f_list:[
				// 	{text:'首页', classR:'homepage'},
				// 	{text:'商城', classR:'stock_right'},
				// 	{text:'购物车', classR:'shopping_cart'},
				// 	{text:'我的', classR:'my'}
				// ]
			}
		},
		methods: {
			toPath:function(e){
				this.index_r = e;
			}
		}
	}
</script>

<style>
	.footer {
		position: fixed;
		left: 0;
		bottom: 0;
		width: 100%;
		height: 98upx;
		display: flex;
		justify-content: space-around;
		background-color: #fff;
		z-index: 9;
		box-sizing: border-box;
		border-top: 1px solid #f0f0f0;
	}
	.footer .navs{
		width: 25%;
	}
	.footer .list {
		height: 98upx;
		width: 100%;
		text-align: center;
		color: #333;
		border-radius: 4upx;
		font-size: 20upx;
	}
	.footer .list .f_icon{
		width: 54upx;
		height: 54upx;
		margin: 6rpx auto 2rpx;
	}
	.footer .list .f_text{
		width: 100%;
	}
	.list.on {
		background: sandybrown;
		color: #fff;
	}
	
	
	.homepage{
		background: url(../static/images/tab_01.png) no-repeat center;
		background-size: 100% 100%;
	}
	.stock_right{
		background: url(../static/images/tab_02.png) no-repeat center;
		background-size: 100% 100%;
	}
	.shopping_cart{
		background: url(../static/images/tab_03.png) no-repeat center;
		background-size: 100% 100%;
	}
	.my{
		background: url(../static/images/tab_04.png) no-repeat center;
		background-size: 100% 100%;
	}
	.homepage.active{
		background: url(../static/images/tab_01_r.png) no-repeat center;
		background-size: 100% 100%;
	}
	.stock_right.active{
		background: url(../static/images/tab_02_r.png) no-repeat center;
		background-size: 100% 100%;
	}
	.shopping_cart.active{
		background: url(../static/images/tab_03_r.png) no-repeat center;
		background-size: 100% 100%;
	}
	.my.active{
		background: url(../static/images/tab_04_r.png) no-repeat center;
		background-size: 100% 100%;
	}
</style>
