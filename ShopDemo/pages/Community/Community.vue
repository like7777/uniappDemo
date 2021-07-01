<template>
	<view class="pics">
		<scroll-view  :scroll-top="0" :scroll-left="0" scroll-y="true" class="left" >
			<view  class="scroll-view-item" :class="isActive == item.cat_id ? 'active' : ''"
				@click="options(item.cat_id)"
				v-for="(item,index) in menu" :key="index">
				{{item.cat_name}}
			</view>
		</scroll-view>
		<scroll-view class="right" scroll-y>
			<view class="" >
				1
			</view>
		</scroll-view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				isActive:1,
				menu:[],
            }
		},
		onLoad() {
			this.getLists() 
		},
		methods: {
			options(e){
				this.isActive = e
			},
			getLists(){
				uni.request({
					url:"https://api-hmugo-web.itheima.net/api/public/v1/categories",
					success : res => {
						this.menu = res.data.message
						console.log(this.menu)
					}
				})
			}
		}
	}
</script>

<style>
	page {
		height: 100%;
	}
	.pics {
		height: 100%;
		display: flex;
	}
	
	.left {
		width: 100px;
		height: 100%;
		display: inline-block;
		border-right: 1px solid #ccc;
	}
	
	.scroll-view-item {
		height: 60px;
		line-height: 60px;
		display: block;
		width: 100px;
		background: #fff;
		border-bottom: 1px solid #ccc;
		text-align: center;
	}
	
	.active {
		color: #fff;
		background: #b50e03;
	}
</style>
