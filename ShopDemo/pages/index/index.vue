<template>
	<view class="content">
		<swiper class="index-swiper" :indicator-dots="false" :autoplay="true" :interval="3000" :duration="1000" >
			<swiper-item v-for="(item,index) in swipers" :key="index">
				<image :src="item"></image>
			</swiper-item>
		</swiper>
		<view class="tips">
			<view class="tipsBlock">
				<view class="rounded">
					<image src="../../static/icon/超市.png" mode=""></image>
				</view>
				<view class="text">
					<text>超市</text>
				</view>
			</view>
			<view class="tipsBlock">
				<view class="rounded">
					<image src="../../static/icon/联系我们.png" mode=""></image>
				</view>
				<view class="text">
					<text>联系</text>
				</view>
			</view>
			<navigator class="tipsBlock" url="../Community/Community">
				<view class="rounded">
					<image src="../../static/icon/社区图片.png" mode=""></image>
				</view>
				<view class="text">
					<text>图片</text>
				</view>
			</navigator>
			<view class="tipsBlock">
				<view class="rounded">
					<image src="../../static/icon/视频.png" mode=""></image>
				</view>
				<view class="text">
					<text>视频</text>
				</view>
			</view>
		</view>
		<view class="recommended">
			<text>推荐商品</text>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				swipers:[]
			}
		},
		onLoad() {
			this.getSwiper()
		},
		methods: {
			getSwiper(){
				console.log('1')
				uni.request({
					url:"https://www.fastmock.site/mock/784cf122fa59703e2622bb68c14518a9/unidemo/api/swipers",
					method:"POST",
					success : res => {
						console.log(res)
						if(res.errMsg == "request:ok"){
							console.log(111)
						}
						this.swipers = res.data
						console.log(this.swipers[0])
					}
				})
			},
		}
	}
</script>

<style>
	.index-swiper{
		width: 100%;
		height: 468upx;
	}
		
	image{
		width: 100%;
	}
	
	.tips {
		display: flex;
		flex-direction: row;
		align-content: stretch;
		justify-content: space-evenly;
		align-items: baseline;
	}
	
	.tips image {
		width: 30px;
		height: 30px;
	}
	
	.rounded {
		border-radius: 50%;
		background: pink;
		width: 50px;
		height: 50px;
		display: flex;
		align-items: center;
		justify-content: center;
	}
	
	.tipsBlock {
		display: flex;
		align-items: center;
		flex-direction: column
	}
	
	.recommended {
		border: 2px  solid #ccc;
		border-left: none;
		border-right: none;
		margin-top: 10px;
		height: 50px;
		line-height: 50px;
		color: red;
	}
	
	.recommended text {
		width: 60%;
		margin: 0 auto;
		display: block;
		text-align: center;
		letter-spacing: 20px;
	}
</style>
