<template>
	<view>
		商品详情页{{imagPath}}
	</view>
</template>

<script>
	export default {
		data() {
			return {
				imagPath:"",
			}
		},
		methods: {
			
		},
		onLoad(req) {
			this.$data.imagPath = req.imagPath;
		}
	}
</script>

<style>

</style>
