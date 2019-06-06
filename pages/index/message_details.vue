<template>
	<view class="container">
		<view class="title">{{detailsItem.title}}</view>
		<view class="hint">
			<span>{{detailsItem.time}}</span>
			<span>{{detailsItem.notice}}</span>
		</view>
		<view class="img_box">
			<image src="../../static/images/message_01.png"></image>
		</view>
		
		<view class="text"></view>
		<text class="text">{{detailsItem.text}}</text>
		
	</view>
</template>

<script>
	export default{
		data(){
			return{
				detailsItem:{
					title:'有房有车：关于股票大幅增长喜报',
					time:'2014-12-15',
					notice:'有房有车官方公告',
					url:'',
					text:'根据中国证券监督管理委员会证监许可[2013]1479号《关于发行股份购买资产并募集配套资金的批复》核准，非公发行股份购买资产并募集配套资金暨重大资产重组实完成后，公司股份总数变更为225,825,711股。伊泽瑞尔专营集团30,651,800股，占公司总股本的13.57%。\n2014年5月21日—2014年9月10日，通过竞价交易及大宗交易方式累计减持8,068,940股，减持后拉克丝专营集团持有公司22,582,860股，占公司总股本的10.00%。\n 根据中国证券监督管理委员会证监许可[2015]1411号《关于核准浙江星星瑞金科技股份有限公司向NEW POPULAR TECHNOLOGY CO.，LTD.等发行股份购买资产并募集配套资金的批复》核准，公司向2015年重大资产重组交易对方发行股份购买资产实施完成后，公司股份总数变更为298,298,305股。国科瑞华持有公司22,582,860股，占公司总股本的7.57%。\n 《星月夜》（The Starry Night）是荷兰后印象派画家文森特·梵·高于1889年在法国圣雷米的一家精神病院里创作的一幅油画，是梵高的代表作之一，现藏纽约现代艺术博物馆。在这幅画中，梵高用夸张的手法，生动地描绘了充满运动和变化的星空。 [1]  整个画面被一股汹涌、动荡的蓝绿色激流所吞噬，旋转、躁动、卷曲的星云使夜空变得异常活跃，脱离现实的景象反映出梵·高躁动不安的情感和疯狂的幻觉世界。'
				}
			}
		}
	}
</script>

<style>
	.container{
		width: 100%;
		padding: 0 20upx 30upx;
		box-sizing: border-box;
		text-align: justify;
	}
	.container .title{
		font-size: 36upx;
		color: #000;
		padding-left: 10upx;
		box-sizing: border-box;
		overflow: hidden;
		text-overflow: ellipsis;
		white-space: nowrap;
	}
	.container .hint{
		font-size: 30upx;
		color: #888;
		margin: 30upx 0 30upx 10upx;
	}
	.container .hint span{
		margin-right: 20upx;
	}
	
	.container .img_box{
		width: 100%;
		height: 390upx;
		margin-bottom: 30upx;
	}
	.container .img_box image{
		width: 100%;
		height: 100%;
	}
	.container .text{
		font-size: 34upx;
		color: #111;
		line-height: 50upx;
		text-align: justify;
	}
</style>
