<template>
	<view class="pics">
		<scroll-view class="left" scroll-y="true">
			<view v-on:click="chose(index,item.id)" v-bind:class="active===index?'active':''" v-for="(item,index) in picsCate" v-bind:key="item.id">{{item.title}}</view>
		</scroll-view>
		<scroll-view class="right" scroll-y="true">
			<view v-for="sitem in secoundDate" v-bind:key="sitem.index">
				<image v-bind:src="sitem.imageUrl"></image>
				<text>{{sitem.imageText}}</text>
			</view>
			
		</scroll-view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				picsCate:[],
				active:0,
				secoundDate:[],
			}
		},
		methods: {
			chose: function(index,id){
				this.$data.active = index;
				//获取右侧的数据,更具传入的id查询
				this.getRightDate(id);
			},
			getRightDate:function(id){
				this.$data.secoundDate = [];
				//根据id查询数据
				if(id == "2")
				{
					this.$data.secoundDate = [
					{
						imageUrl:"../../static/icon/member-active.png",
						imageText:"111"
					},
					{
						imageUrl:"../../static/icon/member-active.png",
						imageText:"222"
					},
					{
						imageUrl:"../../static/icon/member-active.png",
						imageText:"333"
					},
					{
						imageUrl:"../../static/icon/member-active.png",
						imageText:"444"
					}
				];
				}
				
				
			},
			getpicsCate : function(){
				//模拟请求后端接口
				this.$data.picsCate = [
					{
						title:"家居生活1",
						id:"1"
					},
					{
						title:"家居生活2",
						id:"2"
					},
					{
						title:"家居生活3",
						id:"3"
					},
					{
						title:"家居生活4",
						id:"4"
					},
					{
						title:"家居生活5",
						id:"5"
					},
					{
						title:"家居生活6",
						id:"6"
					},
					{
						title:"家居生活7",
						id:"7"
					},
					{
						title:"家居生活8",
						id:"8"
					},
					{
						title:"家居生活9",
						id:"9"
					},
					{
						title:"家居生活10",
						id:"10"
					},
					{
						title:"家居生活11",
						id:"11"
					},
					{
						title:"家居生活12",
						id:"12"
					},
					{
						title:"家居生活13",
						id:"13"
					},
					
					]
			}
					
		},
		onLoad() {
			this.getpicsCate();
			this.getRightDate("0")
		}
	}
</script>

<style lang="scss">
	page{
		height: 100%;
	}
	.pics{
		height: 100%;
		display: flex;
		.left{
			width: 200rpx;
			height: 100%;
			border-right: 1px solid #eee;
			view{
				height: 60px;
				line-height: 60px;
				color: #333;
				text-align: center;
				font-size: 30rpx;
				border-top: 1px solid #eee;
			}
			.active{
				background-color: #B50E03;
				color: #FFFFFF;
			}
			.right{
				height: 100%;
				width: 50rpx;
				margin: 0 auto;
			}
		}
	}
</style>
