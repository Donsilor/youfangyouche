<template>
	<view class="container">
		<view class="list">
			<view class="fl">用户名</view>
			<view class="fr">
				<input class="ipt" type="text" value="" v-model="iptValue" @click="onInput"/>
			</view>
		</view>
		
		<view class="btn_r" :class="{on:this.iptValue}">完成</view>
		
		<view class="bgcolor_r"></view>
	</view>
</template>

<script>
	export default{
		data () {
			return{
				iptValue: '今夜月色温柔'
			}
		},
		methods: {
			onInput(){
				this.iptValue = '';
			}
		}
	}
</script>

<style>
	.list{
		width: 100%;
		height: 100upx;
		background-color: #fff;
		padding: 0 20upx;
		box-sizing: border-box;
		font-size: 30upx;
		color: #333;
		line-height: 100upx;
		margin-top: 20upx;
	}
	.list .fr{
		color: #666;
	}
	.list .fr .ipt{
		width: 540upx;
		height: 60upx;
		margin-top: 20upx;
		text-align: right;
	}

</style>
