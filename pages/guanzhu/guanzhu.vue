<template>
	<view>
		<!-- 导航栏 -->
		<view class="daohang">
			<image class="fanhui" src="../../static/fanhui.svg"></image>
			<view class="xiewenzhang" @click="qw">
				关注
				<view v-if="q==1" class="hongtiao"></view>
			</view>
			<view class="xiewenzhang" @click="qwe">
				粉丝
				<view v-if="q==2" class="hongtiao"></view>
			</view>
		</view>
		<view style="height: 96rpx;"></view>
		<!-- 关注内容 -->
		<view v-if="q==1||w==1" class="neir" v-for="(item,index) in guanzhu">
			<view>
				<image class="tup" :src="item.img"></image>
			</view>
			<view class="ming">{{item.ming}}</view>
			<view :class="[item.w=='关注'?'weiguanzhu':'yiguanzhu']" @click="asss(index)">{{item.w}}</view>
		</view>
		<!-- 粉丝内容 -->
		<view v-if="q==2" class="neir" v-for="(item,index) in fenshi">
			<view>
				<image class="tup" :src="item.img"></image>
			</view>
			<view class="ming">{{item.ming}}</view>
			<view :class="[item.w=='关注'?'weiguanzhu':'yiguanzhu']" @click="ass(index)">{{item.w}}</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				q:'1',
				w:'',  
				e:'1',
				guanzhu:[
					{img:'../../static/head_portrait.jpg',ming:'养乐多',w:'已关注'},
					{img:'../../static/head_portrait.jpg',ming:'养乐多',w:'已关注'},
					{img:'../../static/head_portrait.jpg',ming:'养乐多',w:'已关注'},
					{img:'../../static/head_portrait.jpg',ming:'养乐多',w:'已关注'},
					{img:'../../static/head_portrait.jpg',ming:'养乐多',w:'已关注'},
					{img:'../../static/head_portrait.jpg',ming:'养乐多',w:'已关注'},
					{img:'../../static/head_portrait.jpg',ming:'养乐多',w:'已关注'},
					{img:'../../static/head_portrait.jpg',ming:'养乐多',w:'已关注'},
					{img:'../../static/head_portrait.jpg',ming:'养乐多',w:'已关注'},
					{img:'../../static/head_portrait.jpg',ming:'养乐多',w:'已关注'},
					{img:'../../static/head_portrait.jpg',ming:'养乐多',w:'已关注'},
					{img:'../../static/head_portrait.jpg',ming:'养乐多',w:'已关注'},
				],
				fenshi:[
					{img:'../../static/head_portrait.jpg',ming:'养乐多',w:'已关注'},
					{img:'../../static/head_portrait.jpg',ming:'养乐多',w:'关注'},
					{img:'../../static/head_portrait.jpg',ming:'养乐多',w:'已关注'},
					{img:'../../static/head_portrait.jpg',ming:'养乐多',w:'关注'},
					{img:'../../static/head_portrait.jpg',ming:'养乐多',w:'关注'},
					{img:'../../static/head_portrait.jpg',ming:'养乐多',w:'关注'},
					{img:'../../static/head_portrait.jpg',ming:'养乐多',w:'已关注'},
					{img:'../../static/head_portrait.jpg',ming:'养乐多',w:'关注'},
					{img:'../../static/head_portrait.jpg',ming:'养乐多',w:'已关注'},
					{img:'../../static/head_portrait.jpg',ming:'养乐多',w:'关注'},
					{img:'../../static/head_portrait.jpg',ming:'养乐多',w:'关注'},
					{img:'../../static/head_portrait.jpg',ming:'养乐多',w:'关注'},
				]
			}
		},
		methods: {
			qw(){
				this.q=1
				console.log(this.q)
			},
			qwe(){
				this.q=2
				console.log(this.q)
			},
			ass(index){
				let w = this.fenshi[index].w;
				this.fenshi[index].w = w == '关注' ? '已关注' : '关注'
			},
			asss(index){
				let w = this.guanzhu[index].w;
				this.guanzhu[index].w = w == '关注' ? '已关注' : '关注'
			},
		}
	}
</script>

<style>
	.daohang{
		height: 96rpx;
		line-height: 96rpx;
		display: flex;
		position: fixed;
		z-index: 50;
		border-bottom: 1rpx solid #999999;
		font-size: 32rpx;
		color: #505050;
		width: 100%;
		background-color: #ffffff;
	}
	.xiewenzhang{
		font-size: 40rpx;
		color: #505050;
		margin-left: 28%;
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
		margin-top:15rpx;
		margin-left: 20rpx;
	}
	.yiguanzhu{
		width: 120rpx;
		height: 60rpx;
		font-size: 28rpx;
		background-color: rgba(229, 229, 229, 1);
		border-radius: 10rpx;
		text-align: center;
		line-height: 60rpx;
		color: rgba(56, 56, 56, 1);
		margin-top: 36rpx;
		margin-right: 36rpx;
		margin-left: auto;
	}
	.weiguanzhu{
		width: 120rpx;
		height: 60rpx;
		font-size: 28rpx;
		background-color: rgba(210, 60, 62, 1);
		border-radius: 10rpx;
		text-align: center;
		line-height: 60rpx;
		color: rgba(255, 255, 255, 1);
		margin-top: 36rpx;
		margin-right: 36rpx;
		margin-left: auto;
	}
	.neir{
		height: 138rpx;
		width: 90%;
		display: flex;
		border-bottom: 1rpx solid rgba(153, 153, 153, 0.16);
		margin: auto;
	}
	.tup{
		width: 84rpx;
		height: 84rpx;
		border-radius: 42rpx;
		margin-top: 30rpx;
	}
	.ming{
		font-size: 32rpx;
		margin-left: 46rpx;
		line-height: 138rpx;
	}
	.s{
		background-color: red;
	}
	.ss{
		background-color: blue;
	}
</style>
