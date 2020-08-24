<template>
	<view class="credit">
		<view class="top">
			<view class="header">
				<view class="score">{{creditScore}}</view>
				<view class="text">我的信用分</view>
			</view>
		</view>
		<view class="content">
			<view class="content-list"
				v-for="(item,index) in list"
				:key="index"
			>
				<view class="left">{{item.title}}</view>
				<view class="arrow"></view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				creditScore: 720,
				list: [
					{
						title: '规则解读'
					},
					{
						title: '负面记录'
					}
				]
			}
		},
		onLoad(e) {
			// this.creditScore = e.num
		},
		methods: {
			
		}
	}
</script>

<style lang="scss" scoped>
.credit{
	width: 100%;
	.top{
		display: flex;
		align-items: center;
		width: 180rpx;
		height: 500rpx;
		margin: 0 auto;
		text-align: center;
		.header{
			.score{
				color: rgba(51, 53, 56, 1);
				font-size: 64rpx
			}
			.text{
				margin-top: 30rpx;
				color: rgba(126, 131, 141, 1);
				font-size: 36rpx;
			}
		}
	}
	.content{
		.content-list{
			display: flex;
			justify-content: space-between;
			align-items: center;
			padding: 20rpx 40rpx;
			border-top: 2rpx solid #eee;
			.left{
				color: rgba(50, 50, 51, 1);
				font-size: 16px;
			}
			.arrow{
				width: 16rpx;
				height: 16rpx;
				border-top: 1px solid  rgba(69, 69, 69, 1);
				border-right: 1px solid  rgba(69, 69, 69, 1);
				transform: rotate(45deg);
			}
		}
	}
}
</style>
