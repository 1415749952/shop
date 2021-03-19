<template>
	<view>
		新闻详情页{{id}}
	</view>
</template>

<script>
	export default {
		data() {
			return {
				id:'',
			}
		},
		methods: {
			getNewDetail:function(id){
				console.log(id);
				//向后端发送请求，2绑定数据
			}
		},
		onLoad(options) {
			this.$data.id = options.id;
			this.getNewDetail(this.$data.id);
		}
	}
</script>

<style>

</style>
