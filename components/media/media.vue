<template>
	<view>
		<image class="swiper-item" src="https://apicdn.likepoems.com/images/pc/85057c7d0d87f100da21cbac002dbb2cc.jpg"
			mode="widthFix"></image>
		<c-lottie ref="cLottieRef" :src='src' @LoopComplete="onLoopComplete" width="750rpx" height='750rpx'
			:loop="true"></c-lottie>

	</view>
</template>

<script>
	import animation from "@/static/animation.json"
	export default {
		name: "media",
		onReady() {

			console.log(animation)
		},
		data() {
			return {
				src: animation.toString()
			};
		},
		methods: {
			onLoopComplete() {

			}
		}
	}
</script>

<style>
	/* .content {
		display: flex;
		justify-content: center;
		align-items: center;
		height: 100vh;
	} */
</style>