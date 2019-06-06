<template>
	<view class="container">
		<view class="list">
			<view class="fl left">姓名</view>
			<view class="fr right">
				<input class="ipt" type="text" placeholder="请输入您的姓名" placeholder-style="color:#999">
			</view>
		</view>
		<view class="list">
			<view class="fl left">手机号</view>
			<view class="fr right">
				<input class="ipt" type="text" placeholder="请输入您的手机号" placeholder-style="color:#999"/>
			</view>
		</view>
		<view class="list">
			<view class="fl left">选择首付金额</view>
			<view class="fr right self clf">
				<view class="ite fl clf" v-for="(item, index) in items" :key="index" :class="{active: item.checked}" @click="chooseMoney(index)">
					<span class="circle fl"></span>{{item.name}}
				</view>
			</view>
		</view>
		<view class="list">
			<view class="fl left">持有类型</view>
			<view class="fr right self clf">
				<view class="ite fl clf" v-for="(item, index) in type" :key="index" :class="{active: item.checked}" @click="chooseType(index)">
					<span class="circle fl"></span>{{item.name}}
				</view>
			</view>
		</view>
		<view class="opinion">意见信息</view>
		<textarea class="texts" value="" placeholder="请输入意向区域、户型、面积等 " placeholder-style="color:#999" />
		
		<!-- 可提交时加样式on -->
		<view class="btn_r">提交</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'radio',
				items: [{
						value: '0',
						name: '0首付',
						checked: false
					},
					{
						value: '5',
						name: '5万',
						checked: true
					},
					{
						value: '10',
						name: '10万',
						checked: false
					}
				],
				type: [{
						value:'myself',
						name:'自己持有',
						checked: true
					},
					{
						value:'other',
						name:'代为持有',
						checked: false
					},
				],
				current: 0
			}
		},
		methods: {
			chooseMoney(e){
				this.items.forEach(o => {
					o.checked = false;
					this.items[e].checked = true;
				})
			},
			chooseType(e){
				this.type.forEach(o => {
					o.checked = false;
					this.type[e].checked = true;
				})
			}
		}
	}
</script>

<style>
	.container{
		padding: 20upx;
		box-sizing: border-box;
	}
	.list,
	.opinion{
		width: 100%;
		height: 100upx;
		font-size: 30upx;
		color: #333;
		line-height: 100upx;
		border-bottom: 1upx solid #ddd;
	}
	.list .left{
		width: 180upx;
		height: 100upx;
	}
	.list .right{
		width: 530upx;
		height: 100upx;
		line-height: 100upx;
		box-sizing: border-box;
	}
	.list .self{
		width: auto;
		max-width: 522upx;
	}
	.list .right .ite{
		margin-left: 36upx;
	}
	.list .right .ite .circle{
		width: 46upx;
		height: 46upx;
		border: 1upx solid #ccc;
		border-radius: 50%;
		margin: 26upx 10upx 0 0;
	}
	.list .active .circle{
		border-color: #fc921f !important;
		background: url('https://szdbi.oss-cn-shenzhen.aliyuncs.com/youfangyouche/icon_02.png') no-repeat center;
		background-size: 100% 100%;
	}
	.list .ipt{
		float: right;
		width: 400upx;
		height: 40upx;
		margin-top: 30upx;
		text-align: right;
	}
	.opinion{
		border: none;
	}
	.texts{
		width: 100%;
		height: 400upx;
		padding: 20upx;
		box-sizing: border-box;
		border: 1upx solid #ddd;
		border-radius: 5upx;
	}
	
	/* .uni-list-cell {
		float: right;
		margin-left: 30upx;
	}
	.uni-list-cell radio{
		margin-right: 6upx;
		color: red;
	} */
	

</style>
