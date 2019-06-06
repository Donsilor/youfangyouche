<template>
	<view class="container">
		<view class="bg_img"></view>
		<view class="box">
			<view class="user_img">
				<image src="../../static/images/user.png"></image>
			</view>
		
			<view class="text">填写推荐码</view>
			<view class="recommend clf">
				<view class="my_reco" v-if="1">
					<span class="name">张北平</span>
					<span class="tel">18617179617</span>
				</view>
				<view v-else-if="0">
					<view class="left fl clf">
						<span class="line fl"></span>
						<input class="ipt fl" type="text" placeholder="请输入对方的推荐码">
					</view>
					<view class="right fr">绑定</view>
				</view>
			</view>
			
			<view class="text">我的推荐码</view>
			
			<view class="recommend recommend_my clf">
				<view class="left fl clf">
					<span class="line fl"></span>
					<input class="ipt fl" type="text" value="18617179617" disabled>
				</view>
				<view class="right fr">复制</view>
			</view>
		</view>
		
		<view class="explain">
			<view class="tit">推荐说明</view>
			<view class="txt">豆瓣，一直以书籍、影视作品等优质评分著称。\br而「豆瓣评分」小程序专注于影视作品的评分。打开小程序就能看到热门的电影、电视剧和综艺的评分。在顶部的搜索框可以查询某部影片的评分。
一部作品值不值得看，「豆瓣评分」给你提供一个可靠的参考。豆瓣，一直以书籍、影视作品等优质评分著称。而「豆瓣评分」小程序专注于影视作品的评分。打开小程序就能看到热门的电影、电视剧和综艺的评分。在顶部的搜索框可以查询某部影片的评分。
一部作品值不值得看，「豆瓣评分」给你提供一个可靠的参考。</view>
		</view>
	</view>
</template>

<script>
	export default{
		data () {
			return{
				
			}
		}
	}
</script>

<style>
	.bg_img{
		width: 100%;
		height: 664upx;
		background: url('https://szdbi.oss-cn-shenzhen.aliyuncs.com/youfangyouche/fans_bg.png') no-repeat center;
		background-size: 100% 100%;
		padding-top: 100upx;
		box-sizing: border-box;
	}
	
	.box{
		position: relative;
		width: 100%;
		min-height: 460upx;
		background-color: #fff;
		border-radius: 64upx 64upx 0 0;
		margin-top: -400upx;
		padding: 60upx 20upx 20upx;
		box-sizing: border-box;
	}
	.box .user_img{
		position: absolute;
		top: 0;
		left: 50%;
		transform: translate(-50%, -50%);
		width: 150upx;
		height: 150upx;
		border-radius: 50%;
	}
	.box .user_img image{
		width: 100%;
		height: 100%;
		border-radius: 50%;
	}

	.text{
		font-size: 30upx;
		color: #333;
		margin-top: 60upx;
		text-align: center;
	}
	.recommend{
		width: 610upx;
		height: 100upx;
		margin: 60upx auto;
		border-radius: 8upx;
	}
	.recommend .line{
		width: 5upx;
		height: 44upx;
		background-color: #ff8e06;
		margin: 28upx 20upx 28upx 40upx;
	}
	.recommend .left{
		width: 450upx;
		height: 100upx;
		border: 2upx solid #eee;
		border-right: 0;
		border-radius: 8upx 0 0 8upx;
		box-sizing: border-box;
	}
	.recommend .ipt{
		width: 300upx;
		height: 60upx;
		font-size: 30upx;
		color: #333;
		margin-top: 20upx;
	}
	.recommend .right{
		width: 160upx;
		height: 100upx;
		background-color: #ff8e06;
		font-size: 30upx;
		color: #fff; 
		text-align: center;
		line-height: 100upx;
		border-radius: 0 8upx 8upx 0;
	}
	
	.recommend_my .left{
		border: none;
		background-color: #f6f6ff;
	}
	.recommend_my .left .line{
		background-color: #ff5011;
	}
	.recommend_my .left .ipt{
		color: #505052;
	}
	.recommend_my .right{
		background-color: #ff5011;
	}
	
	.recommend .my_reco{
		width: 100%;
		height: 100upx;
		border: 2upx solid #eee;
		border-radius: 8upx;
		line-height: 100upx;
		text-align: center;
		font-size: 30upx;
		color: #333;
	}
	.recommend .my_reco .name{
		margin-right: 40upx;
	}
	
	.explain{
		width: 710upx;
		margin: 0 20upx 30upx;
	}
	.explain .tit{
		font-size: 30upx;
		color: #999;
		text-align: center;
	}
	.explain .txt{
		font-size: 24upx;
		color: #999;
		line-height: 36upx;
		margin-top: 30upx;
	}
</style>
