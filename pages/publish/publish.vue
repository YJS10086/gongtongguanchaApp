<template>
	<view class="content">
		<navigator url="../../pages/index/index" open-type='switchTab' class="title">返回</navigator>
		<view class="url" >
			发布
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		},
		methods: {
			

			}
	}
</script>

<style>
	.content {
		width: 100%;
		height: 88rpx;
		position: relative;
		display: flex;
		font-size: 30rpx;
		background-color: white;
		color: white;
		border-bottom: 1rpx #999 solid;
	}

	.content .title {
		width: 10%;
		display: flex;
		align-items: center;
		height: 100%;
		padding-left: 20rpx;
		color: black;
	}
	.content .url {
		width: 10%;
		
		position: absolute;
		top: 25rpx;
		right: 0;
		text-align: center;
		padding-right: 20rpx;
		color: #d23c3e;
	}
</style>
