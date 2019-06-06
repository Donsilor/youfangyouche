<template>
	<view class="container">
		<navigator class="address" url="./select_address">
			<view class="icon">
				<i class="iconfont icondizhi1"></i>
			</view>
			<view class="mid">
				<view class="user">
					<span>奥利安娜</span>
					<span>18615121526</span>
				</view>
				<view class="addr">中国浙江省杭州市滨江区网商路699号滨江新园区A座6...</view>
			</view>
			<view class="icon_2">
				<i class="iconfont icongengduo"></i>
			</view>
		</navigator>
		
		<view class="strip"></view>
		
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
						<view class="quantity fr">{{item.num}}</view>
					</view>
				</view>		
			</view>
		</view>
		<view class="box_r">
			<view class="list_r clf">
				<view class="text fl">备注</view>
				<view class="right fr">
					<input class="fr ipt" type="text" value="" placeholder="请输入运费"/>
				</view>
			</view>
			<view class="list_r clf">		
				<view class="fl text">优惠券</view>
				<view class="fr right"  @click="showSinglePicker">请选择
					<span class="fr icon">
						<i class="iconfont icongengduo"></i>
					</span>
				</view>	
			</view>
			<view class="list_r clf">
				<view class="text fl">运费</view>
				<view class="right fr">
					<view class="fr">包邮</view>
				</view>
			</view>
		</view>
		<view class="box_r">
			<view class="list_r clf">
				<view class="text fl">积分抵扣</view>
			</view>
			<view class="list_r clf">
				<view class="color fl">可用积分199，抵扣￥199.00</view>
				<view class="fr switch">
					<view class="uni-list fr">
						<view class="uni-list-cell uni-list-cell-pd">
							<switch />
						</view>
					</view>
				</view>
			</view>
		</view>
		
		<view class="total">
			<view class="fl left">
				<view class="fr text">共{{total}}件,合计：<span class='color'>￥{{pirce}}</span></view>
			</view>
			<view class="fr del">提交订单</view>
			<view></view>
		</view>
		
	</view>
</template>

<script>	
	export default {
		data() {
			return {
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
				// 共多少件商品
				total: 0,
				// 共多少钱
				pirce: 0
			}
		},
		methods: {
			showSinglePicker () {
			},
			onTotal () {
				this.items.forEach(o => {
					this.total += (+o.num);
					this.pirce += (+o.num*o.price)
				})
			}
		},
		mounted () {
			this.onTotal()
		}
	}
</script>

<style>
	page{
		background-color: #f5f5f5;
	}
	.container{
		padding: 0 0 150upx;
	}
	.address{
		width: 100%;
		background-color: #fff;
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
	}
	.box{
		padding: 0 20upx;
		background-color: #fff;
		border-top: 20upx solid #f5f5f5;
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
		background-color: #fff;
		padding: 20upx;
		margin-bottom: 20upx;
	}
	.box_r .list_r{
		height: 50upx;
	}
	.box_r .list_r .text{
		font-size: 26upx;
		color: #333;
		height: 50upx;
		width: 20%;
		line-height: 50upx;
	}
	.box_r .list_r .right{
		height: 50upx;
		width: 60%;
		font-size: 26upx;
		color: #888;
		line-height: 50upx;
		text-align: right;
	}
	.box_r .list_r .right .fr{
		height: 50upx;
		line-height: 50upx;
	}
	.box_r .list_r .right .icon{
		width: 28upx;
		height: 28upx;
		margin: 11upx 0 0 6upx;
		line-height: 32upx;
		color: #ccc;
	}
	.box_r .list_r .right .ipt{
		height: 40upx; 
		text-align: right;
	}
	.box_r .color{
		font-size: 24upx;
		color: #999;
	}
	.box_r .list_r .switch{
		margin-top: -30upx;
	}
	
	.total{
		position: fixed;
		left: 0;
		bottom: 0;
		width: 100%;
		height: 98upx;
		z-index: 6;
	}
	.total .left{
		width: 73%;
		height: 100%;
		background-color: #fff;
		line-height: 98upx;
		font-size: 28upx;
		color: #888;
	}
	.total .left .color{
		color: #ff1919;
	}
	.total .left .icon{
		margin: 24upx 20upx 14upx 28upx;
	}
	.total .left .text{
		margin-right: 1rem;
	}
	.total .del{
		width: 27%;
		height: 100%;
		background: -webkit-linear-gradient(left, #ff8e06, #ff5011);
		text-align: center;
		line-height: 98upx;
		font-size: 32upx;
		color: #fff;
	}
</style>
