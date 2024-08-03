<template>
	<view>
		<image class="swiper-item" src="https://apicdn.likepoems.com/images/pc/85057c7d0d87f100da21cbac002dbb2cc.jpg"
			mode="widthFix"></image>


	</view>
</template>

<script>
	export default {
		name: "media",
		onLoad() {
			console.log('ass')
			console.log(animation)
		},
		data() {
			return {
				src: "./static/animation.json"
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