<template>
	<view class="container">
		<view class="banner">
			<image src="../../static/images/09_02.png"></image>
		</view>
		
		<view class = "integral">
			<navigator class="left" url="../my/integral">
				<span class="iconfont iconjifenduihuan"></span>
				<span class="text">积分</span>
				<span class="num">199</span>
			</navigator>
			<view class="right">
				<span class="iconfont iconjifendingdan"></span>
				<span class="text">兑换记录</span>
			</view>
		</view>
		
		<view class="box clf">
			<view class="fl never">
				<view class="tit">附近商家</view>
				<navigator class="look" url="./nearby">点击查看更多商家</navigator>
				<view class="img_box">
					<image src="../../static/images/shop_00.png"></image>
				</view>
			</view>
			<view class="fr find">
				<view class="tit">发现好货</view>
				<navigator class="look look1" url="./nearby">探索新生活</navigator>
				<view class="wrap">
					<view class="img_box">
						<image src="../../static/images/shop_01.png"></image>
					</view>
					<view class="img_box">
						<image src="../../static/images/shop_02.png"></image>
					</view>
				</view>
				<view class="tit">新品首发</view>
				<navigator class="look look2" url="./nearby">万物皆可盘</navigator>
				<view class="wrap wrap2">
					<view class="img_box">
						<image src="../../static/images/shop_03.png"></image>
					</view>
					<view class="img_box">
						<image src="../../static/images/shop_04.png"></image>
					</view>
				</view>
			</view>
		</view>
		
		<navigator class="line_box clf" url="./all_classify">
			<view class="fl left">
				<span class='fl line'></span>热门分类
			</view>
			<view class="fr right">
				<span class="fr">
					<i class='iconfont icongengduo'></i>
				</span>
				<span class="fr">全部</span>
			</view>
		</navigator>
		
		<navigator class="classify" url="./all_classify">
			<view class="list" v-for="(item, index) in classifyItem" :key="index">
				<view class="left">
					<view class="name">{{item.name}}</view>
					<view class="subhead">{{item.subhead}}</view>
				</view>
				<view class="right">
					<image src="../../static/images/shop_05.png"></image>
				</view>
			</view>
			
		</navigator>
		
		<view class="line_box clf">
			<view class="fl left">
				<span class='fl line'></span>精选推荐
			</view>
		</view>
		
		<view class="content">
			<navigator class="list" v-for="(item, index) in shop_items" :key="index" url="./commodity_details">
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
	export default{
		data () {
			return{
				classifyItem:[
					{
						name:'电脑',
						subhead:'大吉大利今晚吃鸡',
						url:''
					},
					{
						name:'数码',
						subhead:'换新机爆品推荐',
						url:''
					},
					{
						name:'美妆',
						subhead:'合格的吃土少女',
						url:''
					},
					{
						name:'时尚鞋服',
						subhead:'半价爆品限量版',
						url:''
					},
					{
						name:'电脑',
						subhead:'大吉大利今晚吃鸡',
						url:''
					},
					{
						name:'数码',
						subhead:'换新机爆品推荐',
						url:''
					},
					{
						name:'美妆',
						subhead:'合格的吃土少女',
						url:''
					},
					{
						name:'时尚鞋服',
						subhead:'半价爆品限量版',
						url:''
					}
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
		}
	}
</script>

<style>
	.banner{
		width: 100%;
		height: 300upx;
	}
	.banner image{
		width: 100%;
		height: 100%;
	}
	
	
	.integral{
		width: 100%;
		height: 100upx;
		border-bottom: 20upx solid #f5f5f5;
		display: flex;
		align-items: center;
	}
	.integral .left,
	.integral .right{
		width: 50%;
		height: 44upx;
		text-align: center;
		display: flex;
		justify-content: center;
		align-items: center;
	}
	.integral .left{
		border-right: 1upx solid #ddd;
		box-sizing: border-box;
	}
	.integral .iconfont{
		color: #fc9628;
		font-size: 40upx;
	}
	.integral .left .text,
	.integral .right .text{
		font-size: 30upx;
		color: #666;
		margin: 0 20upx;
	}
	.integral .right .text{
		margin-right: 0;
	}
	.integral .num{
		font-size: 30upx;
		color: #fc921f;
	}
	
	.box{
		border-bottom: 20upx solid #f5f5f5;
	}
	.box .never,
	.box .find{
		width: 50%;
		padding: 20upx;
		box-sizing: border-box;
	}
	.box .never{
		border-right: 1upx solid #eee;
	}
	.box .tit{
		font-size: 32upx;
		color: #333;
	}
	.box .look{
		font-size: 28upx;
		margin: 20upx 0;
	}
	.box .never .look{
		color: #ff6a28;
	}
	.box .look1{
		color: #6a8bef;
	}
	.box .look2{
		color: #ff3f89;
	}
	.box .never .img_box{
		width: 270upx;
		height: 250upx;
		margin: 120upx auto 0;
	}
	.box .never .img_box image{
		width: 100%;
		height: 100%;
	}
	.box .wrap{
		width: 100%;
		display: flex;
		justify-content: space-around;
		align-items: center;
		margin-bottom: 30upx;
	}
	.box .wrap2{
		margin-bottom: 0;
	}
	.box .wrap .img_box{
		width: 116upx;
		height: 116upx;
	}
	.box .wrap .img_box image{
		width: 100%;
		height: 100%;
	}
	
	.line_box{
		width: 100%;
		height: 112upx;
		line-height: 112upx;
		padding: 0 20upx;
		box-sizing: border-box;
	}
	.line_box .left{
		font-size: 34upx;
		color: #333;
		font-weight: bold;
	}
	.line_box .left .line{
		width: 10upx;
		height: 30upx;
		background: linear-gradient(top, #ff8e06 ,#ff5011);
		margin: 43upx 10upx 0 0;
	}
	.line_box .right{
		width: 300upx;
		font-size: 28upx;
		color: #999;
		
	}
	.line_box .right .iconfont{
		font-size: 36upx;
		color: #999;
		margin-left: 10px;
		margin-top: 2upx;
	}
	
	.classify{
		display: flex;
		width: 710upx;
		justify-content: space-between;
		flex-wrap: wrap;
		margin-left: 20upx;
	}
	.classify .list{
		width: 350upx;
		height: 150upx;
		background-color: #f8f8f8;
		border-radius: 20upx;
		display: flex;
		justify-content: space-between;
		align-items: center;
		padding-left: 30upx;
		box-sizing: border-box;
		margin-bottom: 10upx;
	}
	.classify .list .left{
		width: 190upx;
		display: flex;
		flex-direction: column;
		justify-content: center;
	}
	.classify .list .left .name{
		font-size: 28upx;
		color: #333;
		margin-bottom: 20upx;
	}	
	.classify .list .left .subhead{
		font-size: 24upx;
		color: #999;
	}
	.classify .list .right{
		width: 120upx;
		height: 80upx;
	}
	.classify .list .right image{
		width: 100%;
		height: 100%;
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

