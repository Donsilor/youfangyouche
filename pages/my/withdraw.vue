<template>
	<view class="container">
		<view class="title">转到银行卡</view>
		
		<view class="add clf mpvue-picker">		
			<view class="uni-padding-wrap uni-common-mt">
				<view class="fl text">添加银行卡</view>
				<view class="fr right"  @click="showSinglePicker">{{pickerText}}
					<i class="fr iconfont icongengduo" v-if="!pickerText"></i>
				</view>
			</view>
			<mpvue-picker :themeColor="themeColor" ref="mpvuePicker" :mode="mode" :deepLength="deepLength" :pickerValueDefault="pickerValueDefault"
			 @onConfirm="onConfirm" @onCancel="onCancel" :pickerValueArray="pickerValueArray"></mpvue-picker>
			<mpvue-city-picker :themeColor="themeColor" ref="mpvueCityPicker" :pickerValueDefault="cityPickerValueDefault"
			 @onCancel="onCancel" @onConfirm="onConfirm"></mpvue-city-picker>			
		</view>
		
		<view class="title">提现金额</view>
		<view class="box">
			<view class="fill clf">
				<span class='fl'>￥</span>
				<input class="fl ipt" type="text" value="" ref="ipt"/>
			</view>
			<view class="text">可提现金额<span>500.00</span>元</view>
		</view>
		
		<view class="btn_r" :class="{on:pickerText && this.$refs.ipt.inputValue}">提现</view>
		<view class="remind">（到账时间：T+1为工作日）</view>
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
			}
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
		width: 100%;
		height: 100%;
		background-color: #f5f5f5;
	}
	.title{
		height: 76upx;
		line-height: 76upx;
		font-size: 28upx;
		color: #999;
		padding: 0 20upx;
		box-sizing: border-box;
	}
	.add{
		height: 100upx;
		padding: 0 20upx;
		box-sizing: border-box;
		background-color: #fff;
		font-size: 30upx;
		line-height: 100upx;
		color: #666;
	}
	.add .text{
		width: 180upx;
		height: 100upx;
	}
	.add .right{
		width: 400upx;
		height: 100upx;
	}
	.box{
		background-color: #fff;
		padding: 0 20upx;
		box-sizing: border-box;
	}
	.box .fill{
		height: 150upx;
		font-size: 50upx;
		line-height: 150upx;
		color: #333;
		border-bottom: 1upx solid #e5e5e5;
	}
	.box .ipt{
		width: 500upx;
		height: 50upx;
		display: inline-block;
		margin: 50upx 0 0 20upx;
	}
	.box .text{
		height: 84upx;
		line-height: 84upx;
		font-size: 26upx;
		color: #999;
	}
	.remind{
		font-size: 24upx;
		color: #999;
		text-align: center;
	}
</style>
