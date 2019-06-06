<template>
	<view class="container">
		<view class="search clf">
			<span class="fl">
				<i class="iconfont icondizhi fl"></i>深圳
			</span>
			<input class="ipt fl" type="text" placeholder="搜索商家" />
			<i class='iconfont iconMagnifier'></i>
		</view>
		<view class="box">
			<navigator class="list" v-for="(item, index) in merchantItem" :key = "index" url="./nearby_details">
				<view class="img_box">
					<image src="../../static/images/111_03.png"></image>
				</view>
				<view class="right">
					<view class="name">{{item.name}}</view>
					<view class="address">{{item.address}}</view>
					<view class="distance">{{item.distance}}</view>
				</view>
			</navigator>
		</view>
	</view>
</template>

<script>
	export default{
		data () {
			return{
				merchantItem:[
					{
						imgUrl:'',
						name:'美宜佳24小时便利店',
						address:'深圳市龙华区大浪路宝龙大厦A903',
						distance:'2.2km'
					},
					{
						imgUrl:'',
						name:'711连锁24小时便利店',
						address:'深圳市龙华区大浪路宝龙大厦A903',
						distance:'2.2km'
					},
					{
						imgUrl:'',
						name:'711连锁24小时便利店',
						address:'深圳市龙华区大浪路宝龙大厦A903',
						distance:'2.2km'
					},
					{
						imgUrl:'',
						name:'711连锁24小时便利店',
						address:'深圳市龙华区大浪路宝龙大厦A903',
						distance:'2.2km'
					},
					{
						imgUrl:'',
						name:'711连锁24小时便利店',
						address:'深圳市龙华区大浪路宝龙大厦A903',
						distance:'2.2km'
					},
					{
						imgUrl:'',
						name:'张西平杂货铺',
						address:'深圳市龙华区大浪路宝龙大厦A903',
						distance:'2.2km'
					},
					{
						imgUrl:'',
						name:'张南平五金水暖店',
						address:'深圳市龙华区大浪路宝龙大厦A903',
						distance:'2.2km'
					},
					{
						imgUrl:'',
						name:'美宜佳24小时便利店',
						address:'深圳市龙华区大浪路宝龙大厦A903',
						distance:'2.2km'
					},
					{
						imgUrl:'',
						name:'711连锁24小时便利店',
						address:'深圳市龙华区大浪路宝龙大厦A903',
						distance:'2.2km'
					}
				]
			}
		}
	}
</script>

<style>
	.container{
		padding-top: 88upx;
	}
	.search{
		position: fixed;
		top: 44px;
		left: 0;
		z-index: 2;
		width: 100%;
		height: 88upx;
		background-color: #f6f6f6;
		padding: 0 40upx;
		box-sizing: border-box;
	}
	.search span{
		width: 100upx;
		height: 88upx;
		font-size: 26upx;
		color: #333;
		line-height: 88upx;
	}
	.search span .icondizhi{
		margin-right: 4upx;
	}
	.search .ipt{
		width: 570upx;
		height: 56upx;
		background-color: #fff;
		border-radius: 10upx;
		margin-top: 16upx;
		text-align: center;
		font-size: 26upx;
	}
	.search .iconMagnifier{
		position: absolute;
		top: 52%;
		left: 45%;
		transform: translateY(-50%);
		color: #333;
	}
	
	.box .list{
		padding: 30upx 20upx;
		box-sizing: border-box;
		display: flex;
	}
	.box .list:not(:last-child){
		border-bottom: 1upx solid #e5e5e5;
	}
	.box .list .img_box{
		width: 120upx;
		height: 120upx;
		margin-right: 20upx;
	}
	.box .list .img_box image{
		width: 100%;
		height: 100%;
	}
	.box .list .right{
		flex: 1;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		height: 120upx;
	}
	.box .list .right .name{
		font-size: 28upx;
		color: #333;
		overflow: hidden;
		text-overflow: ellipsis;
		white-space: nowrap;
	}
	.box .list .right .address{
		font-size: 24upx;
		color: #666;
		overflow: hidden;
		text-overflow: ellipsis;
		white-space: nowrap;
	}
	.box .list .right .distance{
		font-size: 22upx;
		color: #666;
	}
	
	
</style>
