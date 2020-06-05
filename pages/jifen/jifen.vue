<template>
	<view>
		<view class="hongd">
			<view class="hesan">
				<view class="heer">
					<view class="heyi" @click="asa">
						签到
						<!-- <image src="../../static/link.gif"></image> -->
					</view>
				</view>
			</view>
			<view class="jifen">我的积分：{{jifen}}</view>
		</view>
		<view class="duihuan">
			<view class="dhsc">兑换商城</view>
			<view class="shangpin" v-for="item in shangpin">
				<view style="margin-right: 62rpx;">
					<image class="sptp" :src="item.img"></image>
				</view>
				<view>
					<view class="spmz">
						{{item.text}}
					</view>
					<view style="display: flex;">
						<view class="xyjf">{{item.jifen}}积分</view>
						<view :class="[(jifen)>(item.jifen)?'duih':'duihh']">兑换</view>
					</view>
				</view>
			</view>
			<view class="zhanwu">暂无更多商品</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				jifen:5457,
				shangpin:[
					{
						img:'../../static/head_portrait.jpg',
						text:'我是商品名称我是商品名称我是商品名称我是商品名称',
						jifen:'5464'
					},
					{
						img:'../../static/head_portrait.jpg',
						text:'我是商品名称我是商品名称我是商品名称我是商品名称',
						jifen:'5'
					},
					{
						img:'../../static/head_portrait.jpg',
						text:'我是商品名称我是商品名称我是商品名称我是商品名称',
						jifen:'5464'
					},
					{
						img:'../../static/head_portrait.jpg',
						text:'我是商品名称我是商品名称我是商品名称我是商品名称',
						jifen:'464'
					},
					{
						img:'../../static/head_portrait.jpg',
						text:'我是商品名称我是商品名称我是商品名称我是商品名称',
						jifen:'5464'
					}
				]
			}
		},
		methods: {
			asa(){
				this.jifen=this.jifen+5
			}
		}
	}
</script>

<style>
	.hongd{
		height: 168rpx;
		background-color: #d23c3e;
		padding: 40rpx;
		display: flex;
	}
	.daoh{
		height: 96rpx;
		width: 100%;
		text-align: center;
		line-height: 130rpx;
		display: flex;
	}
	.dhsc{
		color: rgba(80, 80, 80, 1);
		font-size: 32rpx;
	}
	.sptp{
		width: 174rpx;
		height: 174rpx;
	}
	.spmz{
		font-size: 28rpx;
		color: rgba(80, 80, 80, 1);
		margin-bottom: 36rpx;
		margin-top: 5rpx;
	}
	.xyjf{
		font-size: 28rpx;
		color: rgba(210, 60, 62, 1);
	}
	.zhanwu{
		width: 100%;
		text-align: center;
		font-size: 24rpx;
		color: #999999;
		margin-top: 40rpx;
	}
	.gongtong {
		color: #ffffff;
		font-size: 40rpx;
		line-height: 250%;
		width: 100%;
	}
	.fanhui{
		position: absolute;
		width: 74rpx;
		height: 74rpx;
		margin-top: 10rpx;
		margin-left: 20rpx;
	}
	.hesan{
		width: 154rpx;
		height: 154rpx;
		background-color: rgba(255, 255, 255, 0.41);
		border-radius: 504rpx;
		display: flex;
		align-items: center;
		margin-left: 104rpx;
	}
	.heer{
		width: 132rpx;
		height: 132rpx;
		background-color: rgba(255, 255, 255, 0.64);
		border-radius: 504rpx;
		margin: auto;
		display: flex;
		align-items: center;
	}
	.heyi{
		width: 108rpx;
		height: 108rpx;
		background-color: rgba(255, 255, 255, 0.64);
		border-radius: 504rpx;
		margin: auto;
		text-align: center;
		line-height: 108rpx;
		font-size: 32rpx;
		color: rgba(210, 60, 62, 1);
		font-weight: bold;
	}
	.jifen{
		height: 154rpx;
		line-height: 154rpx;
		font-size: 28rpx;
		color: #ffffff;
		margin-left: 120rpx;
	}
	.duihuan{
		width: 100%;
		border-radius: 36rpx;
		background-color: #ffffff;
		margin-top: -20rpx;
		padding: 30rpx;
	}
	.duih{
		border-style:solid;
		border-width:1rpx;
		font-size: 28rpx;
		border-radius: 10rpx;
		width: 98rpx;
		height: 54rpx;
		color: rgba(210, 60, 62, 1);
		text-align: center;
		line-height: 54rpx;
		margin-left: auto;
		margin-right: 1rpx;
	}
	.duihh{
		border-style:solid;
		border-width:1rpx;
		font-size: 28rpx;
		border-radius: 10rpx;
		width: 98rpx;
		height: 54rpx;
		color: #999999;
		text-align: center;
		line-height: 54rpx;
		margin-left: auto;
		margin-right: 1rpx;
	}
	.shangpin{
		width: 682rpx;
		border-bottom: 1rpx solid rgba(162, 162, 162, 0.41);
		display: flex;
		padding-top: 46rpx;
		padding-bottom: 46rpx;
	}
</style>
