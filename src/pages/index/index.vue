<template>
	<view class="login-box">
		<view class="btn-box">
			<up-button class="btn-box" type="primary" text="微信登陆" @click="wxLogin"></up-button>
		</view>
	</view>
</template>

<script setup lang="ts">
	import { ref, onMounted } from 'vue';
	const wxLogin = () => {
		wx.login().then(res => {
			console.log(res);

			if (res.code) {
				// wx.request(`https://api.weixin.qq.com/sns/jscode2session?appid=APPID&secret=SECRET&js_code=JSCODE&grant_type=authorization_code`)
				wx.navigateTo({
					url: "/pages/home/index",
				})
			}
		})
	}
</script>

<style lang="scss" scoped>
	.login-box {
		width: 100%;
		padding-top: 100rpx;
	}

	.btn-box {
		width: 200rpx !important;
		margin: 0 auto;
	}
</style>