<template>
	<view class="container">
		<view class="title">仅支持绑定本人的储蓄卡</view>
		<view class="list clf">
			<view class="fl left">持卡人：</view>
			<view class="fr right">
				<input class="ipt" type="text" value="" placeholder="请输入您的姓名"/>
			</view>
		</view>
		
		<view class="list clf mpvue-picker">		
			<view class="uni-padding-wrap uni-common-mt">
				<view class="fl left">银行发卡行：</view>
				<view class="fr right"  @click="showSinglePicker">{{pickerText?pickerText:'请选择'}}
					<span class="fr icon" v-if="!pickerText">
						<i class="iconfont icongengduo"></i>
					</span>
				</view>
			</view>
			<mpvue-picker :themeColor="themeColor" ref="mpvuePicker" :mode="mode" :deepLength="deepLength" :pickerValueDefault="pickerValueDefault"
			 @onConfirm="onConfirm" @onCancel="onCancel" :pickerValueArray="pickerValueArray"></mpvue-picker>
			<mpvue-city-picker :themeColor="themeColor" ref="mpvueCityPicker" :pickerValueDefault="cityPickerValueDefault"
			 @onCancel="onCancel" @onConfirm="onConfirm"></mpvue-city-picker>			
		</view>

		<view class="list clf">
			<view class="fl left">卡号：</view>
			<view class="fr right">
				<input class="ipt" type="text" value="" placeholder="请输入银行卡号"/>
			</view>
		</view>

		<!-- 可以点击时加样式on -->
		<view class="btn_r">立即绑定</view>
	</view>
</template>

<script>
	import mpvuePicker from '../common/mpvuePicker.vue';
	import mpvueCityPicker from '../common/mpvueCityPicker.vue';
	import cityData from '../common/city.data.js';
		
		
	export default {
		components: {
			mpvuePicker,
			mpvueCityPicker
		},
		data() {
			return {
				pickerSingleArray: [{
						label: '中国银行',
						value: 1
					},
					{
						label: '工商银行',
						value: 2
					},
					{
						label: '农业银行',
						value: 3
					},
					{
						label: '建设银行',
						value: 4
					},
					{
						label: '邮政银行',
						value: 5
					},
					{
						label: '交通银行',
						value: 6
					},
					{
						label: '上海银行',
						value: 7
					}
				],
				mulLinkageTwoPicker: cityData,
				cityPickerValueDefault: [0, 0, 1],
				themeColor: '#007AFF',
				pickerText: '',
				mode: '',
				deepLength: 1,
				pickerValueDefault: [0],
				pickerValueArray:[]
			};
		},
		methods: {
			onCancel(e) {
				console.log(e)
			},
			showSinglePicker() {
				this.pickerValueArray = this.pickerSingleArray
				this.mode = 'selector'
				this.deepLength = 1
				this.pickerValueDefault = [0]
				this.$refs.mpvuePicker.show()
			},
			onConfirm(e) {
				this.pickerText = e.label
			}
		},
		onBackPress() {
		  if (this.$refs.mpvuePicker.showPicker) {
			this.$refs.mpvuePicker.pickerCancel();
			return true;
		  }
		  if (this.$refs.mpvueCityPicker.showPicker) {
			this.$refs.mpvueCityPicker.pickerCancel();
			return true;
		  }
		},
		onUnload() {
			if (this.$refs.mpvuePicker.showPicker) {
				this.$refs.mpvuePicker.pickerCancel()
			}
			if (this.$refs.mpvueCityPicker.showPicker) {
				this.$refs.mpvueCityPicker.pickerCancel()
			}
		}
	};
</script>

<style>
	.container{
		position: fixed;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		background-color: #f5f5f5;
	}
	.title{
		height: 76upx;
		font-size: 28upx;
		color: #999;
		line-height: 76upx;
		margin-top: 88upx;
		padding-left: 30upx;
	}
	.list{
		width: 100%;
		height: 100upx;
		background-color: #fff;
		border-bottom: 1upx solid #e5e5e5;
		padding: 0 30upx;
		box-sizing: border-box;
		font-size: 30upx;
		line-height: 100upx;
	}
	.list .left{
		width: 32%;
		height: 100upx;
		color: #666;
	}
	.list .right{
		width: 68%;
		height: 100upx;
		color: #333;
		text-align: right;
	}
	.list .right .ipt{
		float: right;
		width: 100%;
		height: 40upx;
		line-height: 60upx;
		margin-top: 30upx;
		text-align: right;
	}
	.list .right .icon{
		width: 44upx;
		height: 44upx;
		margin: 30upx 0 0 10upx;
		color: #333;
		line-height: 44upx;
	}
	.list .right .icon .icongengduo{
		color: #ccc;
	}
	.heig{
		height: 180upx;
	}
	.heig textarea{
		width: 90%;
		height: 130upx;
		margin-top: 32upx;
		font-size: 30upx;
	}
	
</style>

