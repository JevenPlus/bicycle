<template>
	<view class="main">
		<view class="header">
			<view class="img">
				<view class="cu-avatar round">
					<open-data type="userAvatarUrl"></open-data>
				</view>
			</view>
			<view class="user">
				<view class="user-name">用户名</view>
				<view class="user-tel">13333333333</view>
			</view>
		</view>
		<view class="content">
			<view class="content-list">
				<div class="content-item" 
					v-for="(item,index) in list"
					:key="index"
					@click="toItemDetail(index)"
				>
					<div class="item-left">{{item.title}}</div>
					<div class="item-right">
						详细信息
						<div class="arrow"></div>
					</div>
				</div>
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
						title: '我的钱包',
					},
					{
						title: '信用积分',
					},
					{
						title: '我的行程',
					},
					{
						title: '优惠卷与卡包',
					},
					{
						title: '我的消息',
					},
					{
						title: '招商加盟',
					},
					{
						title: '账号安全',
					},
					{
						title: '授权管理',
					},
					{
						title: '政策协议',
					},
				],
				toItemDetail(num){
					switch(num){
						case 0:
							uni.navigateTo({
								url: '/pages/wallet/wallet',
							})
							break;
						case 1:
							uni.navigateTo({
								url: '/pages/credit/credit',
							})
							break;
						case 6:
							uni.navigateTo({
								url: '/pages/account/account'
							})
							break;
						case 7:
							uni.navigateTo({
								url: '/pages/authorization/authorization'
							})
							break;
						case 8:
							uni.navigateTo({
								url: '/pages/agreement/agreement'
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
		},
		methods: {
			
		}
	}
</script>

<style lang="scss" scoped>
.main{
	.header{
		display: flex;
		align-items: center;
		padding: 36rpx 0 34rpx 40rpx;
		.img{
			width: 142rpx;
			height: 142rpx;
			background-color: #ccc;
			border-radius: 6rpx;
			.cu-avatar{
				width: 100%;
				height: 100%;
				border-radius: 6rpx;
				open-data{
					overflow: hidden;
					width: 100%;
					height: 100%;
					border-radius: 6rpx;
				}
			}
		}
		.user{
			margin-left: 46rpx;
			.user-name{
				height: 20px;
				line-height: 20px;
				color: rgba(50, 50, 51, 1);
				font-size: 18px;
			}
			.user-tel{
				height: 18px;
				line-height: 18px;
				margin-top: 28rpx;
				color: rgba(150, 151, 153, 1);
				font-size: 14px;
			}
		}
	}
	.content{
		.content-list{
			.content-item{
				display: flex;
				justify-content: space-between;
				padding: 20rpx 40rpx;
				border-bottom: 1px solid #eeeeee;
				&:nth-child(6){
					margin-bottom: 60rpx;
				}
				.item-left{
					height: 40rpx;
					line-height: 40rpx;
					color: rgba(50, 50, 51, 1);
					font-size: 32rpx;
					text-align: left;
				}
				.item-right{
					display: inherit;
					justify-content: space-evenly;
					align-items: center;
					color: rgba(150, 151, 153, 1);
					font-size: 28rpx;
					.arrow{
						width: 16rpx;
						height: 16rpx;
						margin-left: 20rpx;
						border-top: 1px solid  rgba(150, 151, 153, 1);
						border-right: 1px solid  rgba(150, 151, 153, 1);
						transform: rotate(45deg);
					}
				}
			}
		}
	}
}
</style>
