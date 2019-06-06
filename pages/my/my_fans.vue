<template>
	<view class="container">
		<view class="bg_img">
			<view class="fans">我的粉丝</view>
			<view class="fans_num">265</view>
			<view class="recommend">本周成功推荐1人</view>
		</view>
		
		<view class="box">
			<view class="tit">
				<span class="line fl"></span>粉丝列表
			</view>
			
			<view class="list" v-for="(item, index) in userItem" :key="index">
				<view class="left">
					<image src="../../static/images/user.png"></image>
				</view>
				<view class="right">
					<view class="user_name">{{item.name}}</view>
					<view class="user_message">
						<span class="tel">{{item.tel}}</span>
						<span class="data">{{item.data}}</span>
						<span class="time">{{item.time}}</span>
					</view>
				</view>
			</view>
			
		</view>
	</view>
</template>

<script>
	export default{
		data () {
			return{
				userItem:[
					{
						url:'',
						name:'总想要透过你的眼睛',
						tel:'13522021252',
						data:'2019/5/1',
						time:'08:35'
					},
					{
						url:'',
						name:'去寻找水仙的倒影',
						tel:'13522021252',
						data:'2019/5/1',
						time:'08:35'
					},
					{
						url:'',
						name:'去寻找水仙的倒影',
						tel:'13522021252',
						data:'2019/5/1',
						time:'08:35'
					},
					{
						url:'',
						name:'去寻找水仙的倒影',
						tel:'13522021252',
						data:'2019/5/1',
						time:'08:35'
					},
					{
						url:'',
						name:'没想到最后却目睹',
						tel:'13522021252',
						data:'2019/5/1',
						time:'08:35'
					},
					{
						url:'',
						name:'一整个宇宙的繁星',
						tel:'13522021252',
						data:'2019/5/1',
						time:'08:35'
					},
					{
						url:'',
						name:'这一秒想在爱里沉溺',
						tel:'13522021252',
						data:'2019/5/1',
						time:'08:35'
					}
				]
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
	.bg_img .fans{
		font-size: 30upx;
		text-align: center;
		color: #fff;
	}
	.bg_img .fans_num{
		font-size: 60upx;
		text-align: center;
		color: #fff;
		margin-top: 20upx;
	}
	.bg_img .recommend{
		font-size: 26upx;
		text-align: center;
		color: #fff;
		margin-top: 20upx;
	}
	.box{
		width: 100%;
		min-height: 300upx;
		background-color: #fff;
		border-radius: 64upx 64upx 0 0;
		margin-top: -280upx;
		padding: 60upx 20upx 20upx;
		box-sizing: border-box;
	}
	.box .tit{
		font-size: 34upx;
		color: #333;
	}
	.box .line{
		width: 10upx;
		height: 30upx;
		background: linear-gradient(top, #ff8e06, #ff5011);
		margin: 8upx 10upx 0 0;
	}
	.box .list{
		width: 100%;
		padding: 30upx 0;
		display: flex;
		align-items: center;
	}
	.box .list:not(:last-child){
		border-bottom: 1upx solid #e5e5e5;
	}
	.box .left{
		width: 100upx;
		height: 100upx;
		border-radius: 50%;
		margin-right: 30upx;
	}
	.box .left image{
		width: 100%;
		height: 100%;
		border-radius: 50%;
	}
	.box .right{
		display: flex;
		flex-direction: column;
		justify-content: space-between;
	}
	.box .right .user_name{
		font-size: 30upx;
		color: #333;
		overflow: hidden;
		margin-bottom: 10upx;
	}
	.box .user_message{
		font-size: 26upx;
		color: #888;
	}
	.box .user_message span{
		margin-right: 20upx;
	}
</style>
