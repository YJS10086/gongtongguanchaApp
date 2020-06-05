<template>
	<view class="content">
		<searchList :isTop='isTop' @isinput="isinput"></searchList>
		<swiperList></swiperList>
		<showsList :inputs='inputs'></showsList>
		<view class="bottom_tip" style="" @click="change()">——人家也是有底线的呢——</view>
	</view>
</template>

<script>
	//搜索框
	import searchList from "../../components/search.vue"
	//轮播图
	import swiperList from "../../components/swiper.vue"
	//内容
	import showsList from "../../components/news_list.vue"
	export default {
		components: {
			searchList,
			swiperList,
			showsList
		},
		data() {
			return {
				//顶部样式
				isTop: 0,
				inputs:""
			}
		},
		onLoad() {

		},
		methods: {
			//底部点击返回顶部
			change() {
				uni.pageScrollTo({
					scrollTop: 0,
					duration: 100
				});
			},
			//获取输入框的内容
			isinput(e){
				this.inputs = e
			}

		},
		onPageScroll: function(e) {
			// console.log(e.scrollTop);//实时获取到滚动的值
			if (e.scrollTop > 0) {
				this.isTop = 1
			} else {
				this.isTop = 0
			}
		},
		
	}
</script>

<style>
	.content {}

	.swiper-box {
		/* height: 150px; */
	}

	.bottom_tip {
		height: 50rpx;
		background-color: #d23c3e;
		display: flex;
		align-items: center;
		justify-content: center;
		font-size: 25rpx;
		color: white;
		opacity: .5;
	}
</style>
