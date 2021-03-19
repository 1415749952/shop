<template>
	<view class="root">
		<image src="../../static/icon/1.png" mode="aspectFit"></image>
		<view class="info">
			<view v-on:click="call">电话号码:400-618-9090</view>
			<view>地址：XXXXXXXXXXX</view>
		</view>
		<map class="map" v-bind:longitude="longitude" v-bind:scale="scale" v-bind:latitude="latitude" v-bind:markers="markers"></map>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				longitude:120.363172,
				latitude:30.312212,
				scale:13,
				markers:[
					{
						longitude:120.363172,
						latitude:30.312212,
						iconPath:"../../static/hmlogo.png",
						width:30,
						height:30
					}
				]
			}
		},
		methods: {
			call:function(){
				uni.makePhoneCall({
					phoneNumber:"18390869225",
				})
			}
		}
	}
</script>

<style lang="scss">
	.info{
		padding: 10rpx 20rpx;
		font-size: 40rpx;
		view{
			line-height: 80rpx;
			border-bottom: 1rpx solid #eee;
		}
	}
	.root{
		width: 100%;
	}
	.map{
		width: 100%;
		height: 750rpx;
	}
	.uni-map {
	    position: relative;
	    width: 370px;
	    height: 380px;
	    display: block;
	}
</style>
