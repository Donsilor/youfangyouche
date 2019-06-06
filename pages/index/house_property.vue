 <template>
	 <view class="container">
		 <view class="banner">
			 <image src="../../static/images/house_banner.png"></image>
		 </view>
		 
		 <view class="apply">
			 <view class="list my">
				 <view class="fl img"></view>
				 <span class="fl">我的购房申请</span>
			 </view>
			 <navigator class="list now" url="./house_apply">
				 <view class="fl img"></view>
				 <span class="fl">立即申请购房</span>
			 </navigator>
		 </view>
		 
		 <view class="title">
			<span class="icon"></span>
			<span class="inline">购房流程</span>
			<span class="icon"></span>
		 </view>
		 <view class="box">
			 <view class="list" v-for="(item, index) in welfareItem" :key = 'index'>
				 <view class="top">
					 <span class='fl line'></span>
					 <span>{{item.title}}</span>
				 </view>
				 <view class="text">{{item.text}}</view>
			 </view>	 
		 </view>
	 </view>
</template>

<script>
	export default{
		data() {
			return{
				welfareItem:[
					{
						title:'流程一',
						text:'人生像条大河，可能风景清丽。人生像条大河，可能风景清丽。人生像条大河，可能风景清丽。人生像条大河，可能风景清丽。人生像条大河，可能风景清丽。人生像条大河，可能风景清丽。'
					},
					{
						title:'流程二',
						text:'人生像条大河，可能风景清丽。人生像条大河，可能风景清丽。人生像条大河，可能风景清丽。人生像条大河，可能风景清丽。人生像条大河，可能风景清丽。人生像条大河，可能风景清丽。'
					},
					{
						title:'流程三',
						text:'人生像条大河，可能风景清丽。人生像条大河，可能风景清丽。人生像条大河，可能风景清丽。人生像条大河，可能风景清丽。人生像条大河，可能风景清丽。人生像条大河，可能风景清丽。'
					}
				]
			}
		}
	}
</script>

<style>
	.banner{
		width: 750upx;
		height: 370upx;
	}
	.banner image{
		width: 100%;
		height: 100%;
	}
	.apply{
		display: flex;
		justify-content: space-around;
		align-items: center;
		width: 750upx;
		height: 110upx;
		font-size: 30upx;
		color: #050505;
		border-bottom: 20upx solid #f5f5f5;
	}
	.apply .list{
		display: flex;
		align-items: center;
	}
	.apply .img{
		width: 74upx;
		height: 74upx;
		margin-right: 20upx;
	}
	.apply .my .img{
		background: url('https://szdbi.oss-cn-shenzhen.aliyuncs.com/youfangyouche/house_01.png') no-repeat center;
		background-size: 100% 100%;
	}
	.apply .now .img{
		background: url('https://szdbi.oss-cn-shenzhen.aliyuncs.com/youfangyouche/house_02.png') no-repeat center;
		background-size: 100% 100%;
	}
	
	.title{
		text-align: center;
	}
	.title .icon{
		display: inline-block;
		width: 34upx;
		height: 18upx;
		background: url('https://szdbi.oss-cn-shenzhen.aliyuncs.com/youfangyouche/house_03.png') no-repeat center;
		background-size: 100% 100%;
	}
	.title .inline{
		display: inline-block;
		font-size: 34upx;
		color: #333;
		font-weight: bold;
		margin: 30upx 10upx;
	}
	.box{
		padding-bottom: 120upx;
		width: 710upx;
		margin-left: 20upx;
	}
	.box .list{
		margin-bottom: 30upx;
	}
	.box .list .top{
		font-size: 40upx;
		color: #333;
		margin-bottom: 10upx;
	}
	.box .list .top .line{
		width: 8upx;
		height: 30upx;
		background-color: #fc921f;
		margin: 12upx 20upx 0 0;
	}
	.box .list .text{
		font-size: 30upx;
		color: #666;
	}

</style>
