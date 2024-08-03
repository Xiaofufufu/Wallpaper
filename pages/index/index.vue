<template>
	<swiper class="swiper" :indicator-dots="true" :autoplay="false" :duration="300" interval="2000" :vertical="true"
		duration="500" :current="currentIndex" @change="handleSwiperChange">
		<swiper-item class="swiper-item" v-for="(item, index) in dataList" :key="index">
			<view v-if="index>currentIndex-2&&index<currentIndex+2">
				<media></media>
			</view>
		</swiper-item>
	</swiper>
</template>

<script>
	import media from '@/components/media/media.vue'
	export default {
		data() {
			return {
				dataList: [],
				currentIndex: 0,
				isAdding: false
			};
		},
		component: {
			media
		},
		onLoad() {
			this.addNewData();
		},
		methods: {
			handleSwiperChange(event) {
				this.currentIndex = event.detail.current;
				// 当滑动到最后一个swiper-item时，设置标志位
				if (this.currentIndex === this.dataList.length - 1 && !this.pendingAdd) {
					this.pendingAdd = true;
					// 延迟添加新数据，确保动画完成
					setTimeout(() => {
						this.addNewData();
						this.addNewData();
						this.addNewData();
						this.addNewData();
						this.addNewData();
					}, 300); // 500ms是动画时间，具体值可以调整
				}
			},
			addNewData() {
				const newData = `Slide ${this.dataList.length + 1}`;
				this.dataList.push(newData);
				this.pendingAdd = false; // 重置标志位
			}
		},
	}
</script>

<style>
	.swiper {
		width: 100%;
		height: 100%;
	}

	.swiper-item {
		width: 100%;
		height: 100%;
	}
</style>