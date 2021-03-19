<template>
	<view>
		<view v-for="item in news" v-bind:key="item.title" v-on:click="jump(item.id)">
			{{item.id}}---{{item.title}}---{{item.date}}
		</view>
	</view>
	
</template>

<script>
	export default {
		name:"news",
		data() {
			return {
				 
			};
		},
		props:['news'],
		methods:{
			jump:function(id){
				this.$emit('itemClick',id);
			}
		}
	}
</script>

<style>

</style>
