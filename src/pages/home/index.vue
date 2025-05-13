<template>
	<view class="home-page">
		<image src="/src/static/home_background.png" mode="aspectFill"
			style="position: fixed;width: 100vw;height: 100vh;z-index:-1;background-color: #eeeeee;">
		</image>
		<view class="main-page">
			<p class="common-btn" @click="goPage(1)">
				接单
			</p>
			<view class="center-content">
				<p class="common-btn">投诉中心</p>
				<p class="common-btn">打手登记</p>
			</view>
			<view class="common-btn">
				后台管理
			</view>
		</view>
	</view>
</template>

<script setup lang="ts">
	const goPage = (type : number) => {
		if (type === 1) {
			console.log(1)
			uni.navigateTo({
				url: '/pages/pickOrder/index',
			})
		}
	}
</script>

<style lang="scss" scoped>
	.home-page {
		display: flex;
		flex-direction: column;
		height: 100vmax;

		.main-page {
			height: 100%;
			display: flex;
			flex-direction: column;
			justify-content: center;
			padding: 80rpx 80rpx 0;

			.background-pic {
				width: 100rpx;
				height: 100rpx;
			}

			.center-content {
				margin: 24rpx 0;
				display: flex;
				justify-content: space-between;
				align-items: center;
			}
		}
	}
</style>