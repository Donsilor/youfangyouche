 <template>
	 <view class="container">
		 <view class="banner"></view>
		 
		 <view class="box">
			 <view class="list" v-for="(item, index) in welfareItem" :key = 'index'>
				 <view class="top">
					 <span class="fl line"></span>
					 <span class="tit">{{item.title}}</span>
				 </view>
				 <view class="text">{{item.text}}</view>
			 </view>	 
		 </view>
		 
		 <navigator class="join" url="./financial_join">￥2980立即成为学员</navigator>
	 </view>
</template>

<script>
	export default{
		data() {
			return{
				welfareItem:[
					{
						title:'专属福利一',
						text:'人生像条大河，可能风景清丽。人生像条大河，可能风景清丽。人生像条大河，可能风景清丽。人生像条大河，可能风景清丽。人生像条大河，可能风景清丽。人生像条大河，可能风景清丽。'
					},
					{
						title:'专属福利二',
						text:'人生像条大河，可能风景清丽。人生像条大河，可能风景清丽。人生像条大河，可能风景清丽。人生像条大河，可能风景清丽。人生像条大河，可能风景清丽。人生像条大河，可能风景清丽。'
					},
					{
						title:'专属福利二',
						text:'人生像条大河，可能风景清丽。人生像条大河，可能风景清丽。人生像条大河，可能风景清丽。人生像条大河，可能风景清丽。人生像条大河，可能风景清丽。人生像条大河，可能风景清丽。'
					},
					{
						title:'专属福利二',
						text:'人生像条大河，可能风景清丽。人生像条大河，可能风景清丽。人生像条大河，可能风景清丽。人生像条大河，可能风景清丽。人生像条大河，可能风景清丽。人生像条大河，可能风景清丽。'
					},
					{
						title:'专属福利二',
						text:'人生像条大河，可能风景清丽。人生像条大河，可能风景清丽。人生像条大河，可能风景清丽。人生像条大河，可能风景清丽。人生像条大河，可能风景清丽。人生像条大河，可能风景清丽。'
					},
					{
						title:'专属福利二',
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
		height: 500upx;
		margin: 0 0 30upx;
		background: url('https://szdbi.oss-cn-shenzhen.aliyuncs.com/youfangyouche/A121.png') no-repeat center;
		background-size: 100% 100%;
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
	.box .list .top .tit{
		font-size: 40upx;
		color: #333;
		font-weight: bold;
	}
	.box .list .text{
		font-size: 30upx;
		color: #666;
	}
	
	.join{
		position: fixed;
		bottom: 0;
		left: 0;
		width: 750upx;
		height: 98upx;
		background: -webkit-linear-gradient(left, #ff8e06, #ff5011);
		text-align:center;
		line-height: 98upx;
		font-size: 32upx;
		color: #fff;
	}
</style>
