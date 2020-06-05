<template>
	<view>
		<!-- 导航栏 -->
		<view class="daohang">
			<image class="fanhui" src="../../static/fanhui.svg"></image>
			<view class="xiewenzhang" @click="qw">
				收藏
				<view v-if="q==1" class="hongtiao"></view>
			</view>
			<view class="xiewenzhang" @click="qwe">
				评论
				<view v-if="q==2" class="hongtiao"></view>
			</view>
			<view class="xiewenzhang" @click="qwer">
				点赞
				<view v-if="q==3" class="hongtiao"></view>
			</view>
		</view>
		<view style="height: 96rpx;"></view>
		<!-- 收藏 -->
		
		<!-- 评论 -->
		<view style="padding: 25rpx;" v-if="q==2" v-for="item in ping">
			<view style="display: flex;">
				<view>
					<image class="tupianp" :src="item.tou"></image>
				</view>
				<view class="mingzhi">
					<view class="mingzhii">{{item.ming}}</view>
					<view class="shijian">{{item.shijian}}</view>
				</view>
				<view class="sanchu">删除</view>
			</view>
			<view class="plnr">{{item.nei}}</view>
			<view class="hezi">
				<view class="ren">
					<view class="rmrb">{{item.ren}}</view>
					<view class="xwnr">
						{{item.rong}}
					</view>
				</view>
				<view style="margin-top: 30rpx;">
					<image class="tp" :src="item.rt"></image>
				</view>
			</view>
		</view>
		<!-- 点赞 -->
	</view>
</template>

<script>
	export default {
		data() {
			return {
				q:'1',
				ping:[
					{
						tou:'../../static/head_portrait.jpg',
						ming:'养乐多多',
						shijian:'10.31',
						nei:'我的评论内容我的评论内容我的评论内容',
						ren:'@人民日报',
						rong:'“三个坚持”夯实强国之基  我是标题我是标题',
						rt:'../../static/luner.png'
					},
					{
						tou:'../../static/head_portrait.jpg',
						ming:'养乐多多',
						shijian:'10.31',
						nei:'我的评论内容我的容我的评论内容我的评论内容我的评评论内容评论内容',
						ren:'@人民日报',
						rong:'“三个坚持”夯实强国之基  我是标题我是标题',
						rt:'../../static/luner.png'
					},
					{
						tou:'../../static/head_portrait.jpg',
						ming:'养乐多多',
						shijian:'10.31',
						nei:'我的评论内容我的评论内容我的评论内容',
						ren:'@人民日报',
						rong:'“三个坚持”夯实强国之基  我是标题我是标题',
						rt:'../../static/luner.png'
					},
					{
						tou:'../../static/head_portrait.jpg',
						ming:'养乐多多',
						shijian:'10.31',
						nei:'我的评论内容我的评论内容我的评论内容',
						ren:'@人民日报',
						rong:'“三个坚持”夯实强国之基  我是标题我是标题',
						rt:'../../static/luner.png'
					},
					{
						tou:'../../static/head_portrait.jpg',
						ming:'养乐多多',
						shijian:'10.31',
						nei:'我的评论内容我的评论内容我的评论内容我的评论内容我的评论内容我的评论内容我的评论内容我的评论内容我的评论内容我的评论内容我的评论内容我的评论内容我的评论内容我的评论内容我的评论内容我的评论内容我的评论内容我的评论内容我的评论内容我的评论内容我的评论内容我的评论内容我的评论内容我的评论内容我的评论内容我的评论内容我的评论内容我的评论内容我的评论内容我的评论内容我的评论内容我的评论内容我的评论内容我的评论内容我的评论内容我的评论内容我的评论内容我的评论内容我的评论内容',
						ren:'@人民日报',
						rong:'“三个坚持”夯实强国之基  我是标题我是标题',
						rt:'../../static/luner.png'
					},
					{
						tou:'../../static/head_portrait.jpg',
						ming:'养乐多多',
						shijian:'10.31',
						nei:'我的评论内容我的评论内容我的评论内容',
						ren:'@人民日报',
						rong:'“三个坚持”夯实强国之基  我是标题我是标题',
						rt:'../../static/luner.png'
					},
				]
			}
		},
		methods: {
			qw(){
				this.q=1
			},
			qwe(){
				this.q=2
			},
			qwer(){
				this.q=3
			},
		}
	}
</script>

<style>
	.tp{
		width: 286rpx;
		height: 182rpx;
	}
	.xwnr{
		font-size: 32rpx;
		color: rgba(80, 80, 80, 1);
	}
	.rmrb{
		margin-bottom: 38rpx;
		font-size: 28rpx;
		color: rgba(80, 80, 80, 1);
	}
	.ren{
		width: 344rpx;
		margin-right: 48rpx;
		margin-top: 20rpx;
	}
	.plnr{
		margin-top: 52rpx;
		font-size: 32rpx;
		color: rgba(80, 80, 80, 1);
		margin-bottom: 32rpx;
		overflow: hidden;
		text-overflow: ellipsis;
		display: -webkit-box;
		-webkit-line-clamp: 3;
		-webkit-box-orient: vertical;
	}
	.shijian{
		font-size: 24rpx;
		color: rgba(128, 128, 128, 1);
	}
	.mingzhii{
		font-size: 32rpx;
		color: rgba(80, 80, 80, 1);
		height: 48rpx;
	}
	.mingzhi{
		margin-left: 38rpx;
		margin-top: 10rpx;
	}
	.hezi{
		height: 238rpx;
		width: 666rpx;
		padding: 20rpx;
		display: flex;
		border-style:solid ;
		border-width:3rpx;
		border-color: rgba(204, 204, 204, 1);
	}
	.tupianp{
		width: 100rpx;
		height: 100rpx;
		border-radius: 500rpx;
	}
	.sanchu{
		margin-right: 2rpx;
		margin-left: auto;
		font-size: 28rpx;
		color: rgba(80, 80, 80, 1);
		height: 100rpx;
		line-height: 80rpx;
	}
	.daohang{
		height: 96rpx;
		line-height: 96rpx;
		display: flex;
		position: fixed;
		z-index: 50;
		border-bottom: 1rpx solid rgba(153, 153, 153, 0.16);
		font-size: 32rpx;
		color: #505050;
		width: 100%;
		background-color: #ffffff;
	}
	.xiewenzhang{
		font-size: 40rpx;
		color: #505050;
		margin-left: 18%;
	}
	.hongtiao{
		background-color: #d23c3e;
		width: 80rpx;
		height: 8rpx;
		margin-top: -8rpx;
	}
	.fanhui{
		position: absolute;
		width: 74rpx;
		height: 74rpx;
		margin-top:17rpx;
		margin-left: 20rpx;
	}
</style>
