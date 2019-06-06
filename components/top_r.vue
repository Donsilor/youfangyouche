<template>
	<view class="com_top">
		<view class="top" :style="{backgroundColor: bgColor,color:color_r,borderBottom:border_color}">
			<view class="left" @click="goBack">
				<i class="iconfont iconfenxiang"></i>
			</view>
			<view class="title">{{title}}</view>
			<view class="right">{{subhead}}</view>
		</view>
	</view>
</template>

<script>
	export default{
		props:{
			parameter: Object
		},
		data () {
			return{
				back: '',
				title: '',
				subhead: '',
				bgColor: 'rgba(255, 255, 255, 0)',
				color_r: 'rgb(255, 255, 255)',
				border_color: '1upx solid rgba(221, 221, 221, 0)'
			}
		},
		methods:{
			appScroll() {
				//浏览器兼容
				let scrollTop = window.pageYOffset || document.documentElement.scrollTop || document.body.scrollTop;
				
				if(scrollTop<101){
					var k = parseInt(scrollTop*(2.55))
				}else{
					k = 255
				}
				let opa = (1/255*k).toFixed(1);
				this.bgColor = 'rgba('+ 255 + ',' + 255 + ',' + 255 + ',' + opa + ')';
				this.color_r = 'rgb('+ (255-k) + ',' + (255-k) + ',' + (255-k) + ')';
				this.border_color = '1upx solid rgb('+ 221 + ',' + 221 + ',' + 221 + ',' + opa + ')';
			},
			goBack() {
				if(this.back == 1){
					uni.switchTab({
						url: 'my'
					})
				}else if(this.back == '全部订单'){
					uni.navigateTo({
						url:'../shopping_cart/all_order'
					})
				}
			},
			headerR() {
				this.back = this.parameter.back;
				this.title = this.parameter.title;
				this.subhead = this.parameter.subhead;
			}
		},
		mounted() {
			window.addEventListener('scroll', this.appScroll),
			this.headerR()
		}
	}
</script>

<style>
	.top{
		position: fixed;
		top: 0;
		left: 0;
		z-index: 20;
		width: 100%;
		height: 80upx;
		background-color: rgba(255, 255, 255, 0);
		color: #fff;
	}

	.top .left{
		position: absolute;
		left: 20upx;
		top: 15upx;
		width: 50upx;
		height: 50upx;
		text-align: left;
		line-height: 50upx;
	}
	.top .right{
		position: absolute;
		right: 20upx;
		top: 0;
		max-height: 260upx;
		height: 80upx;
		font-size: 26upx;
		line-height: 86upx;
	}
	.top .title{
		font-size: 34upx;
		text-align: center;
		line-height: 80upx;
	}
</style>
