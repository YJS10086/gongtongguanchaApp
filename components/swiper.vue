<template>
	<view class="page-section-spacing">
		<swiper class="swiper" 
			indicator-dots="true" 
			autoplay="true" 
			interval="5000" 
			duration="500"
			circular>
			<swiper-item v-for="(item , index) in info" :key="index">
				<image :src="item.content" mode="widthFix"></image>
			</swiper-item>
		</swiper>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				info: [{
				               content: require('@/static/index/1.png')
				           }, {
				               content: require('@/static/index/2.png')
				           }, {
				               content: require('@/static/index/3.png')
				           }]
			}
		},
		methods: {
			
		}
	}
</script>

<style>
	.swiper{
		height: 350rpx;
	}
	
	// swiper-item 里面的图片高度
	swiper-item image{
		width: 100%;
		height: 350rpx;
	}
</style>
