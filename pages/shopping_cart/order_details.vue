<template>
	<view class="container">	
		<view class="bg_img">
			<view class="status">代付款</view>
		</view>
		
		<navigator class="address" url="./select_address">
			<view class="icon">
				<i class="iconfont icondizhi1"></i>
			</view>
			<view class="mid">
				<view class="user">
					<span>奥利安娜</span>
					<span>18615121526</span>
				</view>
				<view class="addr">中国浙江省杭州市滨江区网商路699号滨江新园区A座6滨江新园区A座6</view>
			</view>
			<view class="icon_2">
				<i class="iconfont icongengduo"></i>
			</view>
		</navigator>
		
		<!-- <view class="strip"></view> -->
		
		<view class="line_box">
			<span class="line fl"></span>商品详情
		</view>
		
		<view class="box">
			<view class="list" v-for="(item, index) in items" :key='index'>
				<view class="img_box">
					<image src="/static/images/shoppingCart_01.png"></image>
				</view>
				<view class="right">
					<view class="text">{{item.text}}</view>
					<view>
						<view class="type">{{item.type}}</view>
					</view>
					<view>
						<view class="price fl">
							<span class="small">￥</span>{{item.price}}
						</view>
						<view class="quantity fr">x{{item.num}}</view>
					</view>
				</view>		
			</view>
		</view>
		<view class="box_r">
			<view class="list_r clf">
				<view class="text fl">运费</view>
				<view class="right fr">
					<view class="fr">￥{{other.freight}}</view>
				</view>
			</view>
			<view class="list_r clf">
				<view class="text fl">积分抵扣</view>
				<view class="right fr">
					<view class="fr">￥{{other.integral}}</view>
				</view>
			</view>
			<view class="list_r clf">
				<view class="text fl">优惠券抵扣</view>
				<view class="right fr">
					<view class="fr">￥{{other.coupon}}</view>
				</view>
			</view>
			<view class="list_r clf color">
				<view class="text fl">实付款（含运费）</view>
				<view class="right fr">
					<view class="fr">
						<view class="fr">￥{{price}}</view>
					</view>
				</view>
			</view>
		</view>
		
		
		<view class="line_box">
			<span class="line fl"></span>订单信息
		</view>
		
		
		<view class="box_r box_r2">
			<view class="list_r">
				<view class="text fl">备注：</view>
				<view class="right fl">
					<span>暂无备注</span>
				</view>
			</view>
			<view class="list_r">
				<view class="text fl">订单号：</view>
				<view class="right fl">
					<span class="data">2019/3/35</span>
					<span class="time">15:00:00</span>
				</view>
			</view>
			<view class="list_r">
				<view class="text fl">创建时间：</view>
				<view class="right fl">
					<span class="data">2019/3/35</span>
					<span class="time">15:00:00</span>
				</view>
			</view>
			<view class="list_r">
				<view class="text fl">付款时间：</view>
				<view class="right fl">
					<span class="data">2019/3/35</span>
					<span class="time">15:00:00</span>
				</view>
			</view>
			<view class="list_r">
				<view class="text fl">完成时间：</view>
				<view class="right fl">
					<span class="data">2019/3/35</span>
					<span class="time">15:00:00</span>
				</view>
			</view>
		</view>
		
		<view class="total">
			<view class="fr btn">立即支付</view>
			<view class="fr btn">取消订单</view>
		</view>
		
	</view>
</template>

<script>		
	export default {
		data() {
			return {
				back:'',
				title: '',
				subhead: '',
				items: [{
					isActive: false,
					url:'',
					text: '娇兰臻彩宝石唇膏镜面口红女111111111111111111111111111滋润哑光限量版N214正品',
					type: '白云石纹壳',
					price: '499.00',
					num: '1'
				},
				{
					isActive: false,
					url:'',
					text: 'ONLY夏季新款卡通贴布宽松T恤女',
					type: '白云石纹壳',
					price: '269.00',
					num: '2'
				},
				{
					isActive: false,
					url:'',
					text: 'ONLY夏季新款小清新雪纺甜美连衣裙女',
					type: '白云石纹壳',
					price: '189.00',
					num: '4'
				},
				{
					isActive: false,
					url:'',
					text: '「王者之都」春夏新品 BURBERRY女TB 小号专属标识锁扣包80103331',
					type: '白云石纹壳',
					price: '2999.00',
					num: '1'
				}],
				
				// freight:运费， integral: 积分, coupon: 优惠券
				other:{freight: 0, integral: 20, coupon: 200},
				
				// 共多少件商品
				total: 0,
				// 共多少钱
				price: 0
			}
		},
		methods: {
			onTotal () {
				this.items.forEach(o => {
					this.total += (+o.num);
					this.price += (+o.num*o.price)
				})

				this.price = (+this.price + this.other.freight - this.other.integral - this.other.coupon)
			}
		},
		mounted () {
		}
	}
</script>

<style>
	.container{
		padding-bottom: 120upx;
	}
	.bg_img{
		width: 750upx;
		height: 350upx;
		background: url('https://szdbi.oss-cn-shenzhen.aliyuncs.com/youfangyouche/order_details_01.png') no-repeat center;
		background-size: 100% 100%;
		padding-top: 220upx;
		box-sizing: border-box;
	}
	.bg_img .status{
		font-size: 30upx;
		color: #fff;
		margin-left: 60upx;
	}
	
	.address{
		width: 100%;
		display: flex;
		align-items: center;
		padding: 24upx 0;
	}
	.address .icon{
		width: 32upx;
		height: 38upx;
		margin: 0 20upx;
		line-height: 38upx;
	}
	.address .icon .icondizhi1{
		color: #fc921f;
	}
	.address .mid{
		flex: 1;
		padding-right: 20upx;
		box-sizing: border-box;
	}
	.address .mid .user{
		font-size: 30upx;
		color: #000;
		margin-bottom: 4upx;
		font-weight: bold;
	}
	.address .mid span{
		margin-right: 20upx;
	}
	.address .mid .addr{
		font-size: 24upx;
		color: #666;
	}
	.address .icon_2{
		height: 44upx;
		width: 44upx;
		margin-right: 20upx;
		line-height: 44upx;
		color: #ccc;
	}
	.strip{
		width: 100%;
		height: 10upx;
		background: url('https://szdbi.oss-cn-shenzhen.aliyuncs.com/youfangyouche/cart_icon_01.png') no-repeat center;
		background-size: 100% 100%;
		margin-top: 24upx;
	}
	.line_box{
		width: 100%;
		height: 88upx;
		line-height: 88upx;
		font-size: 30upx;
		color: #333;
		border-top: 20upx solid #f5f5f5;
	}
	.line_box .line{
		width: 6upx;
		height: 26upx;
		background: linear-gradient(top, #ff8e06, #ff5011);
		margin: 32upx 10upx 0 30upx;
	}
	.box{
		padding: 0 20upx;
		border-bottom: 20upx solid #f5f5f5;
	}
	.box .list{
		display: flex;
		align-items: center;
		padding: 30upx 0;
		border-bottom: 1upx solid #eee;
	}
	.box .list .icon,
	.total .all .icon{
		width: 44upx;
		height: 44upx;
		border-radius: 50%;
		margin: 0 20upx;
		border: 1upx solid #ccc;
	}
	.box .list .icon.active,
	.total .all .icon.active{
		border-color: #f70c12;
		background: url('https://szdbi.oss-cn-shenzhen.aliyuncs.com/youfangyouche/icon_02.png') no-repeat center;
		background-size: 100% 100%;
	}
	.box .list .img_box{
		width: 180upx;
		height: 180upx;
		background-color: saddlebrown;
	}
	.box .list .img_box image{
		width: 100%;
		height: 100%;
	}
	.box .list .right{
		flex: 1;
		height: 180upx;
		overflow: hidden;
		margin: 0 20upx;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
	}
	.box .list .right .text{
		font-size: 26upx;
		color: #333;
		overflow: hidden;
		text-overflow:ellipsis;
		display: -webkit-box;
		-webkit-line-clamp: 2;
		-webkit-box-orient: vertical;
		width: 90%;
	}
	.box .list .right .type{
		background-color: #f5f5f5;
		height: 40upx;
		padding: 0 12upx;
		line-height: 40upx;
		font-size: 24upx;
		border-radius: 5px;
		display: inline-block;
	}
	.box .list .right .price{
		color: #f70c12;
		font-size: 30upx;
	}
	.box .list .right .price .small{
		font-size: 20upx;
	}
	.quantity{
		font-size: 26upx;
		color: #666;
	}
	.box_r{
		padding: 20upx;
	}
	.box_r .list_r{
		height: 50upx;
	}
	.box_r .list_r .text{
		font-size: 26upx;
		color: #999;
		height: 50upx;
		width: 30%;
		line-height: 50upx;
		overflow: hidden;
	}
	.box_r .list_r .right{
		height: 50upx;
		width: 60%;
		font-size: 26upx;
		color: #888;
		line-height: 50upx;
	}
	.box_r .list_r .right .fr{
		height: 50upx;
		line-height: 50upx;
	}
	.box_r .list_r .right .icon{
		width: 28upx;
		height: 28upx;
		margin: 11upx 0 0 6upx;
		line-height: 58upx;
		color: #ccc;
	}
	.box_r .list_r .right .ipt{
		height: 40upx; 
		text-align: right;
	}
	.box_r .data{
		margin-right: 20upx;
	}
	.box_r .color .text{
		color: #333;
	}
	.box_r .color .right{
		font-size: 30upx;
		color: #ff8e06;
	}
	.box_r2 .text,
	.box_r2 .right{
		color: #333 !important;
	}
	
	.total{
		position: fixed;
		left: 0;
		bottom: 0;
		width: 100%;
		height: 98upx;
		z-index: 6;
		border-top: 1px solid #ddd;
		background-color: #fff;
	}
	.total .btn{
		width: 200upx;
		height: 60upx;
		margin: 19upx 30upx 0 0;
		border: 1upx solid #ddd;
		border-radius: 30upx;
		font-size: 24upx;
		color: #333;
		text-align: center;
		line-height: 58upx;
	}
	
</style>
