<template>
	<view class="content">
		<text>首页</text>
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
						console.log(this.swipers)
					}
				})
				
			}
		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>
