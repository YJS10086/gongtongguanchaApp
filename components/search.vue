<template>
	<view class="content" :class="isTop==1?'content_top':'' ">
		<view class="title">共同观察</view>
		<view class="input">
			<image mode="widthFix" src="../../static/index/Search.svg"></image>
			<input type="text" placeholder="请输入" v-model="input" @blur="isinput()" />
		</view>
		<view class="url" @click="change()">
			<image src="../../static/index/相机.png"></image>
		</view>

		<view :class="[active==true?'active':'shade']">
			<navigator url="../../pages/publish/publish">
				<image src="../../static/index/active_1.svg"></image>
				发动态
			</navigator>
			<navigator>
				<image src="../../static/index/active_2.svg"></image>
				写文章
			</navigator>
			<navigator>
				<image src="../../static/index/active_3.svg"></image>
				开直播
			</navigator>
		</view>
	</view>
</template>

<script>
	export default {
		props: [
			"isTop"
		],
		data() {
			return {
				input: '',
				active: false
			};
		},
		methods: {
			change() {
				//改变样式
				let active = !this.active;
				this.active = active
				// console.log(active)
				// console.log(this.isTop)
			},
			isinput(){
				this.$emit('isinput',this.input)
			}
		},
		mounted() {
			
		}
	}
</script>

<style>
	.content {
		width: 100%;
		height: 88rpx;
		display: flex;
		font-size: 30rpx;
		background-color: #d23c3e;
		color: white;
		font-weight: bold;
		justify-content: center;
		align-items: center;
	}
	/* 滑动样式 */
	.content_top {
		position: fixed;
		top: 0;
		background: #d23c3e;
		z-index: 9;
		transform: all .25s;
	}

	.content .title {
		flex: 2;
		display: flex;
		justify-content: center;
		align-items: center;
		height: 100%;
	}

	.content .input {
		flex: 4;
		display: flex;
		justify-content: center;
		align-items: center;
		height: 60%;
		background-color: white;
		border-radius: 15rpx;
	}

	.content .input input {
		height: 100%;
		width: 85%;
		padding-left: 10rpx;
		color: #000000;
		font-weight: normal;
	}

	.content .input image{
		height: 60rpx;
		width: 30rpx;
	}

	.content .url {
		flex: 1;
		display: flex;
		justify-content: center;
		align-items: center;
		height: 100%;
		text-align: center;
	}

	.content .url image {
		width: 60rpx;
		height: 60rpx;
	}

	/* 点击显示区域 */
	.shade {
		display: none;
	}

	.active {
		height: 200rpx;
		width: 190rpx;
		position: fixed;
		right: 10rpx;
		top: 88rpx;
		z-index: 1;
		background-color: rgba(0, 0, 0, .5);
		font-weight: normal;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		align-items: center;
		animation: isactive 0.25s;
	}

	@keyframes isactive {
		from {
			opacity: 0;
		}

		to {
			opacity: 1;
		}
	}

	.active navigator {
		width: 100%;
		height: 100%;
		display: flex;
		justify-content: center;
		align-items: center;
		padding: 5rpx;
	}

	.active navigator image {
		width: 30%;
		height: 70%;

	}
</style>
