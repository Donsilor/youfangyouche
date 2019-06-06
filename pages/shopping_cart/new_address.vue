<template>
	<view class="container">
		<view class="list clf">
			<view class="fl left">收货人：</view>
			<view class="fr right">
				<input class="ipt" type="text" value="" placeholder="请填写收货人姓名"/>
			</view>
		</view>
		
		<view class="list clf">
			<view class="fl left">手机号码：</view>
			<view class="fr right">
				<input class="ipt" type="text" value="" placeholder="请填写收货人手机号"/>
			</view>
		</view>
		
		<view class="list clf mpvue-picker">		
			<view class="uni-padding-wrap uni-common-mt">
				<view class="fl left">所在区域：</view>
				<view class="fr right"  @click="showMulLinkageThreePicker">{{pickerText?pickerText:'选择所在区域'}}
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
		
		<view class="list clf heig">
			<view class="fl left">详细地址：</view>
			<view class="fr right">
				<textarea value="" placeholder="街道、楼牌号等" />
			</view>
		</view>
		
		<view class="list clf">
			<view class="fl left">设为默认地址：</view>
			<view class="fr right">
				<view class="uni-list fr">
					<view class="uni-list-cell uni-list-cell-pd">
						<switch />
					</view>
				</view>
			</view>
		</view>
		
		<!-- 可以点击时加样式on -->
		<view class="btn_r">保存</view>
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
			switch1Change: function (e) {
				console.log('switch1 发生 change 事件，携带值为', e.target.value)
			},
			switch2Change: function (e) {
				console.log('switch2 发生 change 事件，携带值为', e.target.value)
			},
			onCancel(e) {
				console.log(e)
			},
			// 三级联动选择
			showMulLinkageThreePicker() {
				this.$refs.mpvueCityPicker.show()
			},
			onConfirm(e) {
				this.pickerText = e.label;
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
		width: 100%;
		padding: 20upx;
		box-sizing: border-box;
	}
	.list{
		width: 100%;
		height: 100upx;
		line-height: 100upx;
		border-bottom: 1upx solid #e5e5e5;
		font-size: 30upx;
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
	}
	.list .right .ipt{
		width: 80%;
		height: 40upx;
		line-height: 60upx;
		margin-top: 30upx;
	}
	.list .right .icon{
		width: 44upx;
		height: 44upx;
		margin-top: 30upx;
		line-height: 44upx;
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
