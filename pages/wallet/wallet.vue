<template>
	<view class="wallent">
		<view class="top">
			<view class="wallent-balance">
				<view class="num">{{wallent}}</view>
				<view class="text">钱包余额</view>
			</view>
			<view class="wallent-balance">
				<view class="num">{{ridingNum}}</view>
				<view class="text">骑行积分</view>
			</view>
		</view>
		<view class="content">
			<view class="content-list">
				<view class="content-item"
					v-for="(item,index) in list"
					:key="index"
					@click="toDetail(index)"
				>
					<view class="title">{{item.title}}</view>
					<view class="arrow"></view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				wallent: 188.0,
				ridingNum: 2689,
				list: [
					{
						title: '充值',
					},
					{
						title: '积分充值',
					},
					{
						title: '明细记录',
					},
				]
			}
		},
		methods: {
			// 详情页
			toDetail(num){
				switch(num){
					case 0:
						uni.navigateTo({
							url: '/pages/recharge/recharge?balance='+this.wallent
						})
						break;
					default: 
						uni.showToast({
							icon: 'none',
							title: '暂无页面'
						})
						break;
				}
			}
		}
	}
</script>

<style lang="scss" scoped>
.wallent{
	width: 100%;
	.top{
		display: flex;
		justify-content: space-around;
		height: 500rpx;
		align-items: center;
		border-top: 2rpx solid #eee;
		.wallent-balance{
			.num{
				height: 92rpx;
				color: rgba(51, 53, 56, 1);
				font-size: 66rpx;
				text-align: center;
			}
			.text{
				height: 56rpx;
				margin: 30rpx;
				color: rgba(126, 131, 141, 1);
				font-size: 36rpx;
				text-align: center;
			}
		}
	}
	.content{
		.content-list{
			.content-item{
				display: flex;
				justify-content: space-between;
				align-items: center;
				padding: 20rpx 40rpx;
				border-top: 2rpx solid #eee;
				.title{
					color: rgba(50, 50, 51, 1);
					font-size: 32rpx;
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
