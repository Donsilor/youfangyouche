<template>
	<view class="container">
		<view class="tab">
			<view class="list" :class="{active: isActive == index}" v-for="(item, index) in tabItem" :key = 'index' @click="clickTab(index)">{{item}}</view>
		</view>
		
		<view class="content">
			<view class="c_list clf" v-for="(item, index) in item_boxs" :key = "index">
				<view class="top clf">
					<view class="fl time">
						<span>{{item.data}}</span>
						<span>{{item.time}}</span>
					</view>
					<view class="fr status">{{item.status}}</view>
				</view>
				
				<view class="box">
					<navigator class="list" v-for="(list, index) in item.list" :key='index' url="./order_details">
						<view class="img_box">
							<image src="/static/images/shoppingCart_01.png"></image>
						</view>
						<view class="right">
							<view class="text">{{list.text}}</view>
							<view>
								<view class="type">{{list.type}}</view>
							</view>
							<view>
								<view class="price fl">
									<span class="small">￥</span>{{list.price}}
								</view>
								<view class="quantity fr">x{{list.number}}</view>
							</view>
						</view>		
					</navigator>
				</view>
				
				<view class="fr total_r">共5件商品，合计：<span>￥1528.00</span></view>
				<view class="fr btn">立即支付</view>
				
			</view>
		</view>
	</view>
</template>

<script>
	export default{
		data(){
			return{
				isActive: 0,
				tabItem:['全部订单','待付款','待发货','待收货','退款/售后'],
				item_boxs:[
					{
						
						data:'2019/4/25',
						time:'16:50',
						status:'待收货',
						list: 
						[{
							isActive: false,
							url:'',
							text: '娇兰臻彩宝石唇膏镜面口红女111111111111111111111111111滋润哑光限量版N214正品',
							type: '白云石纹壳',
							price: '499.00',
							number: '1'
						},
						{
							isActive: false,
							url:'',
							text: 'ONLY夏季新款卡通贴布宽松T恤女',
							type: '白云石纹壳',
							price: '269.00',
							number: '1'
						},
						{
							isActive: false,
							url:'',
							text: 'ONLY夏季新款小清新雪纺甜美连衣裙女',
							type: '白云石纹壳',
							price: '189.00',
							number: '1'
						},
						{
							isActive: false,
							url:'',
							text: '「王者之都」春夏新品 BURBERRY女TB 小号专属标识锁扣包80103331',
							type: '白云石纹壳',
							price: '2999.00',
							number: '1'
						}],
					},
					{
						
						data:'2019/4/25',
						time:'16:50',
						status:'待发货',
						list: 
						[{
							isActive: false,
							url:'',
							text: '娇兰臻彩宝石唇膏镜面口红女111111111111111111111111111滋润哑光限量版N214正品',
							type: '白云石纹壳',
							price: '499.00',
							number: '1'
						},
						{
							isActive: false,
							url:'',
							text: 'ONLY夏季新款卡通贴布宽松T恤女',
							type: '白云石纹壳',
							price: '269.00',
							number: '1'
						},
						{
							isActive: false,
							url:'',
							text: 'ONLY夏季新款小清新雪纺甜美连衣裙女',
							type: '白云石纹壳',
							price: '189.00',
							number: '1'
						},
						{
							isActive: false,
							url:'',
							text: '「王者之都」春夏新品 BURBERRY女TB 小号专属标识锁扣包80103331',
							type: '白云石纹壳',
							price: '2999.00',
							number: '1'
						}],
					}

				]
			}
		},
		methods:{
			clickTab(e){
				this.isActive = e;
			}
		},
		onLoad: function(options){
			this.isActive = options.index;
		}
	}
</script>

<style>
	.tab{
		width: 100%;
		height: 72upx;
		padding: 0 20upx;
		box-sizing: border-box;
		display: flex;
		justify-content: space-between;
		border-bottom: 16upx solid #f5f5f5;
	}
	.tab .list{
		font-size: 26upx;
		color: #333;
	}
	.tab .active{
		color: #f70c12;
	}
	
	.content{
		padding-bottom: 60upx;
	}
	.content .c_list:not(:last-child){
		border-bottom: 20upx solid #f5f5f5;
	}
	.content .c_list .top{
		width: 100%;
		padding: 0 20upx;
		box-sizing: border-box;
		margin-top: 20upx;
		font-size: 26upx;
	}
	.content .c_list .top .time{
		color: #999;
	}
	.content .c_list .top .status{
		color: #f70c12;
	}
	
	.box{
		padding: 0 20upx;
		box-sizing: border-box;
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
		margin-left: 20upx;
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
		border-radius: 5upx;
		display: inline-block;
		font-size: 24upx;
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
	
	.total_r{
		width: 100%;
		font-size: 24upx;
		color: #333;
		text-align: right;
		padding: 0 20upx;
		box-sizing: border-box;
		margin: 30upx 0;
	}
	.total_r span{
		font-size: 28upx;
		color: #333;
		font-weight: bold;
	}
	.btn{
		width: 150upx;
		height: 44upx;
		border: 1upx solid #f70c12;
		color: #f70c12;
		line-height: 40upx;
		text-align: center;
		border-radius: 22upx;
		font-size: 28upx;
		margin: 0 20upx 20upx;
	}
</style>
