<template>
	<view class="recharge">
		<div class="content">
			<input type="text" class="input-money" placeholder="请输入充值金额" />
			<view class="text">当前钱包余额为<text class="money">{{amountMoney ? amountMoney : 0}}</text>元</view>
		</div>
		<view class="select">
			<button 
				class="select-money"
				v-for="(item,index) in moneyList" 
				:key="index" 
				@click="rechargeNum(index)"
			>
				{{item.money}}
			</button>
		</view>	
		<view class="button">
			<button :class="bool ? 'change-color' : 'wechat'" @click="wechatPay">微信支付</button>
			<button :class="bool ? 'alipay' : 'change-color'" @click="alipayPay">支付宝支付</button>
		</view>
		<view class="pay">
			<button class="pay-money" @click="toPay">前往支付</button>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				amountMoney: '',
				bool: true,
				activeClass: '',
				moneyList: [
					{
						money: '30元'
					},
					{
						money: '50元'
					},
					{
						money: '100元'
					},
					{
						money: '200元'
					}
				]
			}
		},
		onLoad(e) {
			this.amountMoney = e.balance
		},
		methods: {
			// 选择充值金额
			rechargeNum(num){
				// switch(num){
				// 	case 0:
				// 		this.activeClass = "red"
				// 		break;
				// 	case 1:
				// 		this.activeClass = "red"
				// 		break;
				// 	case 2:
				// 		this.activeClass = "red"
				// 		break;
				// 	case 3:
				// 		this.activeClass = "red"
				// 		break;
				// }
				// console.log(this.activeClass)
			},
			wechatPay(){
				if(!this.bool){
					this.bool = !this.bool;
				}
			},
			alipayPay(){
				if(this.bool){
					this.bool = !this.bool;
				}
			},
			toPay(){
				
			}
		}
	}
</script>

<style lang="scss" scoped>
.recharge{
	width: 86%;
	margin: 0 auto;
	.content{
		margin-top: 40rpx;
		.input-money{
			width: 100%;
			height: 120rpx;
			padding-left: 20rpx;
			border-radius: 8rpx;
			background-color: rgba(247, 248, 250, 1);
			color: rgba(164, 164, 164, 1);
			font-size: 36rpx;
			text-align: left;
		}
		.text{
			height: 44rpx;
			line-height: 44rpx;
			margin-top: 20rpx;
			color: rgba(126, 131, 141, 1);
			font-size: 16px;
			text-align: left;
			.money{
				color: #1989FA;
				margin: 0 4rpx;
			}
		}
	}
	.select{
		display: flex;
		justify-content: space-between;
		align-items: center;
		margin-top: 36rpx;
		.select-money{
			color: rgba(25, 137, 250, 1);
			font-size: 14px;
			text-align: center;
			background-color: rgba(255, 255, 255, 1);
			border: 1px solid rgba(25, 137, 250, 1);
		}
		.red{
			.select-money{
				color: rgba(25, 137, 250, 1);
				font-size: 14px;
				text-align: center;
				background-color: #1989FA;
				border: 1px solid rgba(25, 137, 250, 1);
			}
		}
	}
	.button{
		display: flex;
		justify-content: space-around;
		margin-top: 100rpx;
		.wechat{
			width: 40%;
			height: 80rpx;
			line-height: 80rpx;
			background-color: #fff;
			color: rgba(96, 98, 102, 1);
			font-size: 16px;
		}
		.alipay{
			width: 40%;
			height: 80rpx;
			line-height: 80rpx;
			background-color: #fff;
			color: rgba(96, 98, 102, 1);
			font-size: 16px;
		}
		.change-color{
			width: 40%;
			height: 80rpx;
			line-height: 80rpx;
			background-color: green;
			color: #ffff;
			font-size: 16px;
		}
	}
	.pay{
		width: 80%;
		height: 44px;
		margin: 174rpx auto 0;
		.pay-money{
			border-radius: 4rpx;
			background-color: #1989FA;
			color: rgba(255, 255, 255, 1);
			font-size: 32rpx;
		}
	}
}
</style>
