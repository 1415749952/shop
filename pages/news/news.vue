<template>
	<view>
		<new-list v-on:itemClick="goDetail" v-bind:news="news"></new-list>
	</view>
</template>

<script>
	import newList from "../../components/newList.vue";
	
	
	export default {
		data() {
			return {
				news:[
					{
						id:"1",
						title:"标题1",
						date:"2021-1-1"
					},
					{
						id:"2",
						title:"标题2",
						date:"2021-1-1"
					},
					{
						id:"3",
						title:"标题3",
						date:"2021-1-1"
					},
					
					
				]
			}
		},
		methods: {
			goDetail:function(id){
				uni.navigateTo({
					url:"../newDetail/newDetail?id="+id,
				})
			}
		},
		components:{
			"new-list" : newList,
		}
	}
</script>

<style>

</style>
