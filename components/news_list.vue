<template>
	<view class="content">
		<navigator :url="'../../pages/news_details/news_details?id='+item.id" class="list" v-for="(item,index) in showsList"
		 :key="index">
			<view class="left_content">
				<view class="title">{{item.title}}</view>
				<view class="bottom">
					<view>{{item.zhiding}}</view>
					<view>{{item.ming}}</view>
					<view :style="item.type==3?'display:none':''">{{item.pinglun}}评论</view>
				</view>
			</view>
			<view v-if="item.type==1">
			</view>
			<view class="right_content" v-if="item.type==2">
				<view class="shows_image" v-for="(item2,index2) in item.image" :key="index2">
					<image mode="widthFix" :src="item2.image"></image>
				</view>
			</view>
			<!-- <view class="bottom_content" v-if="item.type==3">
				<view v-for="(item2,index2) in item.image" :key="index2">
					<image mode="widthFix" :src="item2.image"></image>
				</view>
			</view> -->
		</navigator>
		<button @click="filterist">1111111111111111111</button>
	</view>
</template>

<script>
	export default {
		props: ["inputs"],
		data() {
			return {
				isTop: 1,
				islist: [],
				showsList: [{
						title: '“三个坚持”夯实强国之基是标题夯实强国之基是标题夯实强国之基是标题',
						zhiding: '置顶',
						ming: '央视网新闻',
						pinglun: 655,
						type: 1,
						id: 1
					},
					{
						title: '“三个坚持”夯实强国之基是标题三个坚持夯实强国之基是标题三个坚持夯实强国之基是标题',
						zhiding: '热',
						ming: '央视网新闻',
						pinglun: 655,
						image: [{
							image: '../../static/index/1.png'
						}],
						type: 2,
						id: 2
					},
					// {
					// 	title: '“三个坚持”夯实强国之基是标题',
					// 	image: [{
					// 			image: '../../static/index/1.png'
					// 		},
					// 		{
					// 			image: '../../static/index/2.png'
					// 		},
					// 		{
					// 			image: '../../static/index/3.png'
					// 		}
					// 	],
					// 	type: 3,
					// 	id:3
					// },
					{
						title: '三个坚持”夯实强国之基是标题三个坚持夯实强国之基是标题三个坚持夯实强国之基是标题',
						zhiding: '热',
						ming: '央视网新闻',
						pinglun: 655,
						image: [{
							image: '../../static/index/1.png'
						}],
						type: 2,
						id: 4
					},
					{
						title: '啊啊啊啊啊啊',
						zhiding: '热',
						ming: '央视网新闻',
						pinglun: 655,
						image: [{
							image: '../../static/index/1.png'
						}],
						type: 2,
						id: 5
					},
					{
						title: '表表表',
						zhiding: '热',
						ming: '华东网',
						pinglun: 655,
						image: [{
							image: '../../static/index/1.png'
						}],
						type: 2,
						id: 6
					}
				]
			}
		},
		methods: {
			filterist() {
				console.log(this.inputs);
				var arr = []
				this.showsList.forEach((item) => arr.push(item))
				if (this.inputs) {
					arr = this.showsList.filter(item => item.title.includes(this.inputs))
				}
				console.log(arr)
				//转存数据
				this.islist = this.showsList
				//数据赋值
				this.showsList = arr
				//判断输入框内容是否为空
				this.inputs ==undefined? this.showsList = this.islist :'';
			}
		},
		mounted() {

		},
		onLoad() {},
		computed: {


		}
	}
</script>

<style>
	.content {
		width: 98%;
		position: relative;
		margin: 0 auto;
	}

	.list {
		width: 100%;
		border-bottom: 1rpx #999 solid;
		position: relative;
		display: flex;

	}

	.list {
		font-size: 25rpx;
	}

	.list .left_content .title {
		font-size: 30rpx;
		margin: 15rpx;
		font-weight: 500;
		text-indent: 1em;
	}

	.list .left_content .bottom {
		display: flex;
	}

	.list .left_content .bottom view {
		margin: 20rpx;
	}

	.list .left_content .bottom :first-child {
		color: red;
	}

	/* 类型2的显示方式 */
	.left_content {
		flex: 2;
	}

	.right_content {
		flex: 1;
	}

	.list .right_content .shows_image {
		height: 100%;
		display: flex;
		justify-content: center;
		align-items: center;
	}

	.list .right_content .shows_image image {
		width: 80%;

	}

	/* 类型3的显示方式 */
	/* .list .bottom_content {
		flex: 1;
		
	}

	.list .bottom_content view {
		width: 100%;
		display: flex;
		flex-direction: row;
	}

	.list .bottom_content view image {
		flex: 1;
	} */
</style>
