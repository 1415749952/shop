<template>
	<view>
		<goods-list v-bind:goodsIn="goods" v-on:jumpGoodsDetail="jumpGoodsDetail"></goods-list>
		<view v-if="flag">我是有底线的</view>
	</view>
</template>

<script>
	import goodsList from '../../components/goodsList.vue'
	export default {
		data() {
			return {
				flag:false,
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
		methods: {
			getGoodsList: function(){
				//发送后端请求，把接口数据绑定到goods
				console.log("模拟发送后端请求，把接口数据绑定到goods");
			},
			//跳转到到商品详情页
			jumpGoodsDetail:function(imagPath){
				uni.navigateTo({
					url:"../goodsDetail/goodsDetail?imagPath="+imagPath,
				})
			}
		},
		onLoad() {
			this.getGoodsList();
		},
		onReachBottom() {
			console.log("触底了！！！！S");
			var total = 15;
		/* 	//当前页数乘以每一页的数据量 大于等于总数时
			this.$data.flag = true; 
			并不向后端发送请求
			 */
			
			//发送后端请求获取第二页的数据
			var resGoods = this.$data.goods;
			this.$data.goods = [...this.$data.goods,...resGoods];
		},
		onPullDownRefresh() {
			console.log("下拉刷新了");
			/* 
				1、像后端发送请求第一页的数据
				2、将this.$data.goods设成空数组
				3、将this.$data.flag = false; 不显示到底了
				4、数据加载完成后就调用uni.stopPullDownRefresh();关闭自动更新
			 */
			uni.stopPullDownRefresh();
		},
		components:{
			"goods-list":goodsList,
		}
	}
</script>

<style>

</style>
