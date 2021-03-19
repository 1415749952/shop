<template>
		<view class="good-list">
			<view v-for="good in goodsIn" v-on:click="jump(good.imagPath)">
				<image v-bind:src="good.imagPath"></image>
				<text>{{good.xianjia}}-----</text>
				<text>{{good.yuanjia}}----</text>
				<text>{{good.miaoshu}}</text>
			</view>
		</view>
</template>

<script>
	export default {
		name:"goodsList",
		data() {
			return {
				
			};
		},
		props:["goodsIn"],
		methods:{
			jump:function(imagPath){
				this.$emit("jumpGoodsDetail",imagPath);
			}
		}
	}
</script>

<style>

</style>
