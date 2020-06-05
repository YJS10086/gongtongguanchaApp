<template>
	<view class="content">
		<view class="news_title">{{newsdetails.title}}</view>
		<view class="news_user">
			<view class="user_image">
				<image mode="widthFix" :src="newsdetails.user.user_image"></image>
			</view>
			<view class="user_content">
				<view class="user_name">{{newsdetails.user.user_title}}</view>
				<view class="user_bottom">
					<view>{{newsdetails.user.type}}</view>
					<view>{{newsdetails.user.time}}</view>
					<view>{{newsdetails.user.tips}}</view>
				</view>
			</view>
			<view :class="[newsdetails.user.status==1?'active':'news_guanzhu']">
				<view @click="change()">{{newsdetails.user.status==1? "已关注":"关注"}}</view>
			</view>
		</view>
		<view class="news_content">
			<view class="content_main">{{newsdetails.content}}</view>
			<view class="content_image">
				<image mode="widthFix" :src="newsdetails.news_image"></image>
			</view>
			<view class="content_looked">{{newsdetails.looks}}阅读</view>
		</view>

		<!-- 内容以下及评论区 -->
		<view class="other">
			<image mode="widthFix" :src="newsdetails.other.image"></image>
			<view>广告</view>
		</view>
		<view class="active_list" v-for="(item,index) in newsdetails.List" :key="index">
			<view class="active_img">
				<image :src="item.image"></image>
			</view>
			<view class="active_main">
				<view class="main_top">
					<view>{{item.name}}</view>
					<view>{{item.number}}</view>
				</view>
				<view class="main_center">{{item.content}}</view>
				<view></view>
			</view>
		</view>
		<!-- 底部tabbar -->
		<view class="bottom_tabbar">
			<view class="left_1">
				<view class="left_1_content">
					<view>
						<image mode="widthFix" src="../../static/newsList/input.png"></image>
					</view>
					<input type="text" placeholder="请输入" />
				</view>
			</view>
			<view class="left_2">
				<image mode="widthFix" src="../../static/newsList/xiaoxi.png"></image>
			</view>
			<view class="left_3">
				<image mode="widthFix" src="../../static/newsList/shoucang.png"></image>
			</view>
			<view class="left_4">
				<image mode="widthFix" src="../../static/newsList/dianzan.png"></image>
			</view>
			<view class="left_5">
				<image mode="widthFix" src="../../static/newsList/fenxiang.png"></image>
			</view>
		</view>
	</view>

</template>

<script>
	export default {
		data() {
			return {
				newsdetails: {
					user: {
						user_image: require("../../static/newsList/53.png"),
						user_title: "互联网乱建秀",
						type: "原创",
						time: "9月27日",
						tips: "优秀创作者",
						status: "1"
					},
					id: "",
					title: "“三个坚持”夯实强国之基是标题夯实强国之基是标题夯实强国之基是标题",
					content: "三个坚持”夯实强国之基是标题夯实强国之基是标题夯实强国之基是标题三个坚持”夯实强国之基是标题夯实强国之基是标题夯实强国之基是标题三个坚持”夯实强国之基是标题夯实强国之基是标题夯实强国之基是标题三个坚持”夯实强国之基是标题夯实强国之基是标题夯实强国之基是标题三个坚持”夯实强国之基是标题夯实强国之基是标题夯实强国之基是标题",
					news_image: require("../../static/newsList/217.jpg"),
					looks: "16",
					other: {
						image: require("../../static/newsList/214.png")
						//广告
					},
					List: [ //评论
						{
							name: "好先生",
							image: require("../../static/newsList/3.jpg"),
							content: "有习主席这样的好领袖，我们祖国会越来越好，越来越强大。",
							time: "",
							number: 162
						},
						{
							name: "好先生",
							image: require("../../static/newsList/3.jpg"),
							content: "有习主席这样的好领袖，我们祖国会越来越好，越来越强大。",
							time: "",
							number: 162
						}
					]
				},

			}
		},
		methods: {
			change() {
				let status = this.newsdetails.user.status
				this.newsdetails.user.status = (status == 1 ? 0 : 1)
				// console.log(this.newsdetails.user.status)
			}
		},
		onLoad(options) {
			console.log(options.id);
			this.newsdetails.id = options.id
			// 对象传参的接收方法
			// //this.leadobj = JSON.parse(decodeURIComponent(options.leadobj));   
		}
	}
</script>

<style lang="less">
	.content {
		width: 100%;
		padding-bottom: 92rpx;
	}

	.news_title {

		font-size: 35rpx;
		padding: 10rpx;
		text-indent: 1em;
	}

	.news_user {
		display: flex;
		width: 100%;
		height: 100rpx;
		margin: 50rpx 0;
	}

	.user_image {
		flex: 1;
		display: flex;
		justify-content: center;
		align-items: center;

		image {
			width: 86rpx;
			height: 86rpx;
		}
	}

	.user_content {
		flex: 2;

		.user_name {
			margin: 5rpx 0;
			font-weight: bold;
		}

		.user_bottom {
			display: flex;
			font-size: 25rpx;
			align-items: center;

			view:nth-child(1) {
				border: 1rpx #666 solid;
				border-radius: 5rpx;
			}

			view {
				margin: 5rpx;
			}
		}
	}

	.active {
		flex: 1;
		display: flex;
		justify-content: flex-end;
		align-items: center;
		padding-right: 20rpx;

		view {
			background-color: #666;
			width: 60%;
			height: 50%;
			border-radius: 5rpx;
			color: white;
			font-size: 30rpx;
			display: flex;
			justify-content: center;
			align-items: center;

		}
	}

	.news_guanzhu {
		flex: 1;
		display: flex;
		justify-content: flex-end;
		align-items: center;
		padding-right: 20rpx;

		view {
			background-color: #d23c3e;
			width: 60%;
			height: 50%;
			border-radius: 5rpx;
			color: white;
			font-size: 30rpx;
			display: flex;
			justify-content: center;
			align-items: center;

		}
	}

	.news_content {
		padding: 20rpx;

		.content_main {
			text-indent: 1em;
		}

		.content_image {
			margin: 50rpx 0;

			image {
				width: 100%;
			}
		}

		.content_looked {
			font-size: 25rpx;
		}
	}

	// <!-- 内容以下及评论区 -->
	.other {
		position: relative;
		width: 100%;

		image {
			width: 100%;
		}

		view {
			position: absolute;
			left: 20rpx;
			top: 20rpx;
			border: 1rpx #666 solid;
			border-radius: 20rpx;
			font-size: 20rpx;
			background-color: #666;
			opacity: .5;
		}
	}

	.active_list {
		display: flex;
		height: 200rpx;

		.active_img {
			flex: 1;
			display: flex;
			justify-content: center;
			align-items: center;

			image {
				width: 100rpx;
				height: 100rpx;
				border-radius: 50%;
			}
		}

		.active_main {
			flex: 4;
			display: flex;
			flex-direction: column;
			justify-content: center;
			padding-right: 20rpx;

			.main_top {
				display: flex;
				justify-content: space-between;
				font-size: 35rpx;
				margin: 15rpx 0;
			}

			.main_center {
				font-size: 30rpx;
			}
		}
	}

	//底部tabbars
	.bottom_tabbar {
		position: fixed;
		bottom: 0;
		left: 0;
		width: 100%;
		height: 92rpx;
		background: white;
		display: flex;

		.left_1 {
			flex: 3;
			display: flex;
			justify-content: center;
			align-items: center;
			.left_1_content{
				width: 80%;
				height: 60%;
				background: rgba(224, 224, 224, 1);
				border-radius: 30rpx;
				display: flex;
				align-items: center;
				justify-content: center;
				view{
					width: 30%;
					display: flex;
					align-items: center;
					justify-content: center;
					image{
						width: 30rpx;
						height: 100rpx;
					}
				}
				input {
					width: 70%;
					height: 60%;
				}
			}
		}

		.left_2 {
			flex: 1;
			display: flex;
			justify-content: center;
			align-items: center;

			image {
				width: 40rpx;
				height: 90rpx;
			}
		}

		.left_3 {
			flex: 1;
			display: flex;
			justify-content: center;
			align-items: center;

			image {
				width: 40rpx;
				height: 90rpx;
			}
		}

		.left_4 {
			flex: 1;
			display: flex;
			justify-content: center;
			align-items: center;

			image {
				width: 40rpx;
				height: 90rpx;
			}
		}

		.left_5 {
			flex: 1;
			display: flex;
			justify-content: center;
			align-items: center;

			image {
				width: 40rpx;
				height: 90rpx;
			}
		}
	}
</style>
