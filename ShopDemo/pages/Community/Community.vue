<template>
	<view>
		<scroll-view  :scroll-top="scrollTop" :scroll-left="scrollLeft" scroll-y="true" class="scroll-Y" >
				<view  class="scroll-view-item " @click="options(1)" :class="isActive == 1 ? 'active' : ''">家居生活</view>
				<view  class="scroll-view-item " @click="options(2)" :class="isActive == 2 ? 'active' : ''">摄影设计</view>
				<view  class="scroll-view-item " @click="options(3)" :class="isActive == 3 ? 'active' : ''">明星美女</view>
				<view  class="scroll-view-item " @click="options(4)" :class="isActive == 4 ? 'active' : ''">空间设计</view>
				<view  class="scroll-view-item " @click="options(5)" :class="isActive == 5 ? 'active' : ''">户型装饰</view>
				<view  class="scroll-view-item " @click="options(6)" :class="isActive == 6 ? 'active' : ''">广告摄影</view>
				<view  class="scroll-view-item " @click="options(7)" :class="isActive == 7 ? 'active': ''">摄影学习</view>
				<view  class="scroll-view-item " @click="options(8)" :class="isActive == 8 ? 'active' : ''">摄影器材</view>
				<view  class="scroll-view-item " @click="options(9)" :class="isActive == 9 ? 'active' : ''">明星写真</view>
				<view  class="scroll-view-item " @click="options(10)" :class="isActive == 10 ? 'active' : ''">清纯甜美</view>
				<view  class="scroll-view-item " @click="options(11)" :class="isActive == 11 ? 'active' : ''">一二三四</view>
				<view  class="scroll-view-item " @click="options(12)" :class="isActive == 12 ? 'active' : ''">我不知道</view>
		</scroll-view>
		<view class="">
			1234
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				isActive:1,
				scrollTop:100,
				scrollLeft:100
			}
		},
		methods: {
			options(e){
				this.isActive = e
			}
		}
	}
</script>

<style>
	.scroll-Y {
		width: 100px;
		display: inline-block;
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
