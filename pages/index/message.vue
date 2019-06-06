<template>
	<view class="container">
		<view class="banner">
			<image src="../../static/images/message_01.png"></image>
		</view>
		<view class="title">官方通知公告</view>
		<view class="box">
			<navigator class="list" v-for="(item, index) in messageItem" :key="index" url="./message_details">
				<view class="tit">{{item.title}}</view>
				<view class="content">
					<view class="img_box">
						<image src="../../static/images/message_02.png"></image>
					</view>
					<view class="right">
						<view class="text">{{item.text}}</view>
						<view class="time">{{item.time}}</view>
					</view>
				</view>
			</navigator>
		</view>
	</view>
</template>

<script>
	export default{
		data(){
			return{
				messageItem:[
					{
						url:'',
						title:'有房有车企业年度创意海报征集',
						text:'本届大赛主题为“设计创新•产业转型•智造未来”，参赛者由中国大陆、港澳台地区以及世界范围内的设计界人士组成，旨在促进大...创意设计产',
						time:'2019-1-20'
					},
					{
						url:'',
						title:'有房有车增值税率调整通知函（紧急）',
						text:'由于增值税率调整，2019年4月1日起将有16%调至13%。',
						time:'2019-1-20'
					},
					{
						url:'',
						title:'有房有车企业年度创意海报征集',
						text:'本届大赛主题为“设计创新•产业转型•智造未来”，参赛者由中国大陆、港澳台地区以及世界范围内的设计界人士组成，旨在促进大...创意设计产',
						time:'2019-1-20'
					},
					{
						url:'',
						title:'有房有车增值税率调整通知函（紧急）',
						text:'由于增值税率调整，2019年4月1日起将有16%调至13%。',
						time:'2019-1-20'
					},
					{
						url:'',
						title:'有房有车企业年度创意海报征集',
						text:'本届大赛主题为“设计创新•产业转型•智造未来”，参赛者由中国大陆、港澳台地区以及世界范围内的设计界人士组成，旨在促进大...创意设计产',
						time:'2019-1-20'
					},
					{
						url:'',
						title:'有房有车增值税率调整通知函（紧急）',
						text:'由于增值税率调整，2019年4月1日起将有16%调至13%。',
						time:'2019-1-20'
					}
				]
			}
		}
	}
</script>

<style>
	.banner{
		width: 750upx;
		height: 300upx;
	}
	.banner image{
		width: 100%;
		height: 100%;
	}
	.title{
		width: 690upx;
		height: 84upx;
		line-height: 84upx;
		font-size: 26upx;
		color: #a9a9a9;
		margin: 0 30upx;
	}
	
	.box{
		width: 690upx;
		margin: 0 30upx;
	}
	.box .list{
		padding: 30upx 0;
		border-top: 1upx solid #f5f5f5;
	}
	.box .list .tit{
		font-size: 34upx;
		color: #000;
	}
	.box .list .content{
		display: flex;
		width: 100%;
		margin: 30upx 0;
	}
	.box .list .content .img_box{
		width: 120upx;
		height: 120upx;
		background-color: #FDB404;
		margin-right: 30upx;
	}
	.box .list .content .img_box image{
		width: 100%;
		height: 100%;
	}
	.box .list .content .right{
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		flex: 1;
		font-size: 26upx;
	}
	.box .list .content .right .text{
		color: #666;
		display: -webkit-box;
		-webkit-box-orient:vertical;
		-webkit-line-clamp:3;
		overflow: hidden;
		margin-bottom: 10upx;
	}
	.box .list .content .right .time{
		color: #a9a9a9;
	}
</style>
