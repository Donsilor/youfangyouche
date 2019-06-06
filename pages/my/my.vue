<template>
	<view class="container">
		<view class="top_bgcolor">
			<view class="user clf">
				<view class="user_img fl">
					<image src="../../static/images/user.png"></image>
				</view>
				<view class='fl'>
					<view class="clf">
						<view class='user_name fl'>风平浪静</view>
						<view class="rank fl">
							<span class='fl circle'>
								<i class='iconfont iconxingxing'></i>
							</span>
							<span class='fl'>学员</span>
						</view>
					</view>
					<view class="user_id">ID：5263225</view>
				</view>
			</view>
			
			<view class="integral clf">
				<navigator class="fl integral_r" url="./integral">
					<view class="num">3662</view>积分
				</navigator>
				<navigator class="fr integral_r" url="./happiness">
					<view class="num">5233</view>幸福指数
				</navigator>
				<span class='line'></span>
			</view>
		</view>
		
		<view class="my_order">
			<view class="tit">我的订单</view>
			<view class="order_box">
				<navigator class="list" url="../shopping_cart/all_order?index=1">
					<view class="icon icon1"></view>待付款
				</navigator>
				<navigator class="list" url="../shopping_cart/all_order?index=2">
					<view class="icon icon2"></view>待发货
				</navigator>
				<navigator class="list" url="../shopping_cart/all_order?index=3">
					<view class="icon icon3"></view>待收货
				</navigator>
				<navigator class="list" url="../shopping_cart/all_order?index=4">
					<view class="icon icon4"></view>已完成
				</navigator>
				<navigator class="list" url="../shopping_cart/all_order?index=0">
					<view class="icon icon5"></view>全部订单
				</navigator>
			</view>
		</view>
		
		<view class="my_box">
			<navigator class="list" url="./my_fans">
				<span class='fl icon'>
					<i class='iconfont iconhuiyuan'></i>
				</span>我的粉丝
			</navigator>
			<navigator class="list" url="./recommend">
				<span class='fl icon'>
					<i class='iconfont icondianzan'></i>
				</span>我的推荐码
			</navigator>
			<navigator class="list" url="../shopping_cart/select_address">
				<span class='fl icon'>
					<i class='iconfont icondizhi'></i>
				</span>收货地址管理
			</navigator>
			<view class="list">
				<span class='fl icon'>
					<i class='iconfont iconkefu1'></i>
				</span>联系客服
			</view>
			<navigator class="list" url="./set">
				<span class='fl icon'>
					<i class='iconfont iconshezhi'></i>
				</span>设置
			</navigator>
		</view>

	</view>
</template>

<script>	
	export default{
		data () {
			return{
				index: ''
			}
		}
	}
</script>

<style>
	.container{
		position: fixed;
		left: 0;
		top: 0;
		width: 100%;
		height: 100%;
		background: #f5f5f5;
	}
	.top_bgcolor{
		width: 100%;
		height: 494upx;
		background: url('https://szdbi.oss-cn-shenzhen.aliyuncs.com/youfangyouche/personal_01.png') no-repeat center;
		background-size: 100% 100%;
		padding-top: 128upx;
		box-sizing: border-box;
		/* margin-top: -80upx; */
	}
	.top_bgcolor .user{
		height: 80upx;
	}
	.top_bgcolor .user .user_img{
		width: 80upx;
		height: 80upx;
		background-color: #fff;
		border-radius: 50%;
		text-align: center;
		line-height: 80upx;
		margin: 0 30upx;
	}
	.top_bgcolor .user .user_img image{
		width: 100%;
		height: 100%;
		border-radius: 50%;
	}
	.top_bgcolor .user .user_name{
		font-size: 30upx;
		color: #fff;
		margin-right: 30upx;
	}
	.top_bgcolor .user .rank{
		width: 96upx;
		height: 30upx;
		background: linear-gradient(to right, #57575c, #363b3f, #0f0e15);
		border-radius: 15upx;
		line-height: 30upx;
		margin-top: 8upx;
		font-size: 24upx;
		color: #fff;
	}
	.top_bgcolor .user .rank .circle{
		width: 30upx;
		height: 30upx;
		background: linear-gradient(top left, #f8d986, #cea048);
		border-radius: 50%;
		margin-left: -2upx;
		margin-right: 8upx;
		text-align: center;
		line-height: 28upx;
	}
	.top_bgcolor .user .rank .circle .iconxingxing{
		font-size: 22upx;
		color: #fff;
	}
	.top_bgcolor .user .user_id{
		font-size: 26upx;
		color: #fff;
		margin-top: 10upx;
	}
	.integral{
		width: 690upx;
		margin: 50upx 30upx 0 30upx;
		position: relative;
	}	
	.integral .integral_r{
		width: 50%;
		text-align: center;
		font-size: 26upx;
		color: #fff;
	}
	.integral .num{
		font-size: 50upx;
		color: #fff;
		margin-bottom: 10upx;
	}
	.integral .line{
		position: absolute;
		top: 50%;
		left: 50%;
		transform: translate(-50%, -50%);
		height: 60upx;
		width: 1upx;
		border-left: 1upx solid #fff;
	}
	.my_order{
		width: 710upx;
		hegiht: 256upx;
		background-color: #fff;
		border-radius: 10upx;
		margin: -100upx 0 0 20upx;
		padding: 40upx 0;
		box-sizing: border-box;
	}
	.my_order .tit{
		font-size: 34upx;
		color: #333;
		margin-left: 30upx;
	}
	.my_order .order_box{
		display: flex;
		justify-content: space-around;
		align-items: center;
		margin-top: 40upx;
	}
	.my_order .order_box .list{
		font-size: 24upx;
		color: #333;
		text-align: center;
	}
	.my_order .order_box .list .icon{
		width: 68upx;
		height: 62upx;
		margin: 0 auto 20upx;
	}
	.my_order .icon1{
		background: url('https://szdbi.oss-cn-shenzhen.aliyuncs.com/youfangyouche/my_icon_01.png') no-repeat center center;
		background-size: 64upx 62upx;
	}
	.my_order .icon2{
		background: url('https://szdbi.oss-cn-shenzhen.aliyuncs.com/youfangyouche/my_icon_02.png') no-repeat center center;
		background-size: 60upx 56upx;
	}
	.my_order .icon3{
		background: url('https://szdbi.oss-cn-shenzhen.aliyuncs.com/youfangyouche/my_icon_03.png') no-repeat center center;
		background-size: 68upx 60upx;
	}
	.my_order .icon4{
		background: url('https://szdbi.oss-cn-shenzhen.aliyuncs.com/youfangyouche/my_icon_04.png') no-repeat center center;
		background-size: 60upx 54upx;
	}
	.my_order .icon5{
		background: url('https://szdbi.oss-cn-shenzhen.aliyuncs.com/youfangyouche/my_icon_05.png') no-repeat center center;
		background-size: 48upx 56upx;
	}
	
	.my_box{
		width: 710upx;
		background-color: #fff;
		border-radius: 10upx;
		margin: 20upx;
		padding: 0 20upx;
		box-sizing: border-box;
	}
	.my_box .list{
		height: 100upx;
		font-size: 30upx;
		color: #333;
		line-height: 100upx;
	}
	.my_box .list .icon{
		width: 36upx;
		height: 36upx;
		margin-right: 20upx;
		margin-top: 36upx;
		text-align: center;
		line-height: 36upx;
	}
	.my_box .list .icon .iconfont{
		color: #ff7e00;
		font-size: 34upx;
	}
	.my_box .list:not(:last-child){
		border-bottom: 1upx solid #ddd;
	}

</style>
