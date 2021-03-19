<template>
	<view>
		<swiper indicator-dots="true" circular="true">
			<swiper-item v-for="item in swipers" v-bind:key= "item.id">
				<image v-bind:src="item.url" mode="aspectFit"></image>
			</swiper-item>
		</swiper>
		<view class="nava">
			<view class="nava-item" v-for="item in navas" v-bind:key="item.text" v-on:click="jump(item.pageurl)">
				<view v-bind:class="item.yanshi"></view>
				<text>{{item.text}}</text>
			</view>
		</view>
		<view class="hot-goods">
			推荐商品
		</view>
		<goods-list v-bind:goodsIn="goods" v-on:jumpGoodsDetail="jumpGoodsDetail"></goods-list>
	</view>
</template>

<script>
	import goodsList from '../../components/goodsList.vue'
	
	
	export default {
		data() {
			return {
				swipers: [],
				navas:[
					{
						text:"超市",
						yanshi:"iconfont icon-ziyuan",
						pageurl:"../goods/goods"
					},
					{
						text:"联系我们",
						yanshi:"iconfont icon-guanyuwomen",
						pageurl:"../guanyuwomen/guanyuwomen"
					},
					{
						text:"社区图片",
						yanshi:"iconfont icon-tupian",
						pageurl:"../tupian/tupian"
					},
					{
						text:"学习视频",
						yanshi:"iconfont icon-shipin",
						pageurl:"../shipin/shipin"
					},
				],
				goods:[
					{
						imagPath:"dizhi1",
						yuanjia:"yuanjia1",
						xianjia:"xianjia1",
						miaoshu:"miaoshu1",
					},
					{
						imagPath:"dizhi2",
						yuanjia:"yuanjia2",
						xianjia:"xianjia2",
						miaoshu:"miaoshu2",
					},{
						imagPath:"dizhi3",
						yuanjia:"yuanjia3",
						xianjia:"xianjia3",
						miaoshu:"miaoshu3",
					},{
						imagPath:"dizhi4",
						yuanjia:"yuanjia4",
						xianjia:"xianjia4",
						miaoshu:"miaoshu4",
					},{
						imagPath:"dizhi5",
						yuanjia:"yuanjia5",
						xianjia:"xianjia5",
						miaoshu:"miaoshu5",
					},{
						imagPath:"dizhi6",
						yuanjia:"yuanjia6",
						xianjia:"xianjia6",
						miaoshu:"miaoshu6",
					},{
						imagPath:"dizhi7",
						yuanjia:"yuanjia7",
						xianjia:"xianjia7",
						miaoshu:"miaoshu7",
					},{
						imagPath:"dizhi8",
						yuanjia:"yuanjia8",
						xianjia:"xianjia8",
						miaoshu:"miaoshu8",
					},{
						imagPath:"dizhi9",
						yuanjia:"yuanjia9",
						xianjia:"xianjia9",
						miaoshu:"miaoshu9",
					},{
						imagPath:"dizhi10",
						yuanjia:"yuanjia10",
						xianjia:"xianjia10",
						miaoshu:"miaoshu10",
					},{
						imagPath:"dizhi11",
						yuanjia:"yuanjia11",
						xianjia:"xianjia11",
						miaoshu:"miaoshu11",
					},{
						imagPath:"dizhi12",
						yuanjia:"yuanjia12",
						xianjia:"xianjia12",
						miaoshu:"miaoshu12",
					},{
						imagPath:"dizhi13",
						yuanjia:"yuanjia13",
						xianjia:"xianjia13",
						miaoshu:"miaoshu13",
					},{
						imagPath:"dizhi14",
						yuanjia:"yuanjia14",
						xianjia:"xianjia14",
						miaoshu:"miaoshu14",
					},{
						imagPath:"dizhi15",
						yuanjia:"yuanjia15",
						xianjia:"xianjia15",
						miaoshu:"miaoshu15",
					},
				]
			}
		},
		onLoad() {
			this.getSwipers();
		},
		methods: {
			//获取轮播图的数据
			getSwipers:function(){
				/* uni.request({
					url:"/Swipers/getSwipers",
					method:"GET",
					success: (res) => {
							
							this.$data.swipers = res.data
							console.log("-------",this.$data.swipers);
					}, 
				})*/
				
				const res = this.$myRequest({
					url:"/Swipers/getSwipers",
					method:"get",
				})
				/* //设置将后端的数据赋值给swipers
				this.$data.swipers = res; */
				this.$data.swipers = [
					{
						"id":"1",
						"url":"../../static/icon/1.png",
						},
					{
						"id":"2",
						"url":"../../static/icon/2.png"
					}
				];
			},
			jump:function(pageurl){
				uni.navigateTo({
					url:pageurl
				})
				console.log(pageurl);
			},
			//跳转到到商品详情页
			jumpGoodsDetail:function(imagPath){
				uni.navigateTo({
					url:"../goodsDetail/goodsDetail?imagPath="+imagPath,
				})
			}
		},
		components:{
			"goods-list" : goodsList
		}
	}
</script>




<style lang="scss">
	.home{
		.swiper{
			width: 750rpx;
			height: 380rpx;
			.image{
				height: 100%;
				width: 100%;
			}
		}
		
		.nava{
			display: flex;
			.nava_item{
				width: 25%;
			}
		}
		.hot-goods{
			background-color: "#eee";
			height: 50rpx;
			line-height: 50rpx;
		} 
	}
	
/* 	
	.swiper{
		width: 750rpx;
		height: 380rpx;
		image{
			height: 100%;
			width: 100%;
		}
	}
	
	.nava{
		display: flex;
		.nava_item{
			width: 25%;
		}
	}
	.hot-goods{
		background-color: "#eee";
		height: 50rpx;
		line-height: 50rpx;
	} */
	
</style>
