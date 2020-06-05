<template>
	<view>
		<!-- 轮播图 -->
		<swiperList></swiperList>
		<!-- 内容 -->
		<view class="neirong" v-for="qwe in qwer" @click="Jump(qwe.id)">
			<!-- 单张图样子 -->
			<view style="display: flex;" v-if="qwe.qw.length==1">
				<view>
					<text style="width: 464rpx;color: #505050;font-size: 32rpx;">{{qwe.titly}}</text>
					<view style="margin-top: 10rpx;">
						<text class="zhiding">{{qwe.zhiding}}</text>
						<text class="xinwen">{{qwe.ming}}</text>
						<text class="ping">{{qwe.pinglun}}评论</text>
					</view>
				</view>
				<view style="margin-left: 48rpx;">
					<view class="tuhe" v-for="asdf in qwe.qw">
						<image class="tupian" :src="asdf"></image>
					</view>
				</view>
			</view>
			<!-- 多张图样子 -->
			<view v-if="qwe.qw.length!=1&&qwe.qw.length!=''">
				<view style="margin-bottom: 30rpx;">{{qwe.titly}}</view>
				<view style="display: flex;">
					<view class="tuhe" v-for="asdf in qwe.qw">
						<image class="tupian" :src="asdf"></image>
					</view>
				</view>
			</view>
			<!-- 无图样子 -->
			<view v-if="qwe.qw.length==''">
				<view>{{qwe.titly}}</view>
				<view style="margin-top: 10rpx;">
					<text class="zhiding">{{qwe.zhiding}}</text>
					<text class="xinwen">{{qwe.ming}}</text>
					<text class="ping">{{qwe.pinglun}}评论</text>
				</view>
				<view style="display: flex;">
					<view class="tuhe" v-for="asdf in qwe.qw">
						<image class="tupian" :src="asdf"></image>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	//轮播图
	import swiperList from "../../components/swiper.vue"
	export default {
		components: {
			swiperList,},
		data() {
			return {
				// 帖子
				qwer: [
					{
						titly: '“三个坚持”夯实强国之基是标题',
						zhiding: '置顶',
						ming: '央视网新闻',
						pinglun: '655',
						qw: ['../../static/lunyi.png'],
						id:1
					},
					{
						titly: '“三个坚持”夯实强国之基是标题',
						zhiding: '置顶',
						ming: '央视网新闻',
						pinglun: '655',
						qw: ['../../static/lunyi.png', '../../static/lunyi.png'],
						id:2
					},
					{
						titly: '“三个坚持”夯实强国之基是标题',
						zhiding: '热',
						ming: '央视网新闻',
						pinglun: '655',
						qw: [],
						id:3
					},
					{
						titly: '“三个坚持”夯实强国之基是标题',
						zhiding: '置顶',
						ming: '央视网新闻',
						pinglun: '655',
						qw: ['../../static/lunyi.png', '../../static/lunyi.png', '../../static/lunyi.png'],
						id:4
					},
				],
			}
		},
		methods: {
				Jump(e){
					uni.navigateTo({
						url:"../../pages/news_details/news_details?id="+e
					})
				}
		}
	}
</script>

<style>
	.gongtong {
		color: #ffffff;
		font-size: 40rpx;
		line-height: 250%;
	}

	.swiper {
		height: 350rpx;
	}

	// swiper-item 里面的图片高度
	swiper-item image {
		width: 100%;
		height: 350rpx;
	}

	.neirong {
		width: 96%;
		margin-left: auto;
		margin-right: auto;
		margin-top: 40rpx;
		padding-bottom: 40rpx;
		border-bottom: 1rpx solid #f2f2f2;
	}

	.tupian {
		width: 204rpx;
		height: 150rpx;
	}

	.tuhe {
		width: 204rpx;
		height: 150rpx;
		margin-left: 20rpx;
		margin-right: 20rpx;
	}

	.xinwen {
		color: #505050;
		font-size: 24rpx;
		margin-left: 20rpx;
		margin-right: 20rpx;
	}

	.zhiding {
		color: #d23c3e;
		font-size: 24rpx;
		margin-left: 20rpx;
	}

	.ping {
		color: #505050;
		font-size: 24rpx;
	}
</style>
