<template>
	<view class="author">
		<view class="title">
			授权管理
		</view>
		<view class="content">
			<view class="content-list">
				<view class="content-item"
					v-for="(item,index) in list"
					:key="index"
				>
					<view class="check-box">
						<checkbox-group>
							<label>
								<checkbox class="checkbox" :checked="item.checked" value="cb"></checkbox>
							</label>
						</checkbox-group>
					</view>
					<view class="right">
						<div class="item-title">{{item.title}}</div>
						<div class="item-detail">{{item.content}}</div>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list: [
					{
						title: '定位权限',
						content: '用于提供基于位置的查询和导航服务'
					},
					{
						title: '消息通知权限',
						content: '用于发送车辆状态、扣费等通知信息'
					},
					{
						title: '蓝牙权限',
						content: '用于车辆开锁'
					}
				]
			}
		},
		methods: {
			
		}
	}
</script>

<style lang="scss" scoped>
.author{
	.title{
		height: 33px;
		margin-top: 40rpx;
		color: rgba(51, 53, 56, 1);
		font-size: 24px;
		text-align: center;
	}
	.content{
		margin-top: 100rpx;
		.content-list{
			width: 84%;
			margin: 0 auto;
			.content-item{
				display: flex;
				align-items: center;
				height: 80rpx;
				background-color: rgba(247, 248, 250, 1);
				margin-top: 24rpx;
				padding: 20rpx 40rpx;
				border-radius: 8rpx;
				.check-box{
					
				}
				.right{
					margin-left: 34rpx;
					.item-title{
						height: 18px;
						line-height: 18px;
						color: rgba(25, 137, 250, 1);
						font-size: 17px;
						text-align: left;
					}
					.item-detail{
						height: 20px;
						margin-top: 10rpx;
						color: rgba(181, 181, 181, 1);
						font-size: 14px;
						text-align: left;
					}
				}
			}
		}
	}
}
</style>
