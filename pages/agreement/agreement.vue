<template>
	<view class="agreement">
		<div class="title">
			政策协议
		</div>
		<div class="content">
			<div class="content-list">
				<div class="content-item"
					v-for="(item,index) in list"
					:key="index"
				>
					<div class="item-left">{{item.name}}</div>
					<div class="arrow"></div>
				</div>
			</div>
		</div>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list: [
					{
						name: '用户协议'
					},
					{
						name: '隐私协议'
					},
					{
						name: '充值协议'
					},
					{
						name: '押金规则'
					},
					{
						name: '信用积分规则'
					},
				]
			}
		},
		methods: {
			
		}
	}
</script>

<style lang="scss" scoped>
.agreement{
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
				display: flex;justify-content: space-between;
				align-items: center;
				height: 52rpx;
				background-color: rgba(247, 248, 250, 1);
				margin-top: 24rpx;
				padding: 20rpx 40rpx;
				border-radius: 8rpx;
				.item-left{
					color: rgba(102, 102, 102, 1);
					font-size: 30rpx;
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
}
</style>
