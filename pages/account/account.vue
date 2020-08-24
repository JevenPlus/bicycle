<template>
	<view class="account">
		<view class="title">
			账号安全
		</view>
		<view class="phone">更换手机号</view>
		<view class="content">
			<view class="content-list">
				<view class="content-item"
					v-for="(item,index) in list"
					:key='index'
				>
					<view class="item-title">{{item.title}}</view>
					<input class="item-input" type="text"  @input="getAccountNumInfo" v-model="item.value" :placeholder="item.placeholder">
				</view>
			</view>
			<view class="code">
				<view class="code-title">验证码</view>
				<view class="code-right">
					<input class="code-input" type="text" @input="inputCode" placeholder="请输入验证码">
					<view class="code-num" @click="getCode">获取验证码</view>
				</view>
			</view>
			<button class="btn" @click="confirmChange">确认更换</button>
		</view>
		<view class="bottom" @click="cancelAccountNum">注销账号</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				oldNum: '',  // 原手机号
				newNum: '',  // 新手机号
				code: '',  // 验证码
				list: [
					{
						title: '原手机号',
						placeholder: '请输入之前的手机号'
					},
					{
						title: '新手机号',
						placeholder: '请输入现在的手机号',
					}
				]
			}
		},
		methods: {
			getAccountNumInfo(){
				this.oldNum = this.list[0].value
				this.newNum = this.list[1].value
			},
			// 获取输入的验证码
			inputCode(e){
				this.code = e.detail.value
			},
			// 获取验证码
			getCode(){
				
			},
			// 确认更换手机按钮
			confirmChange(){
				
			},
			// 注销账号
			cancelAccountNum(){
				
			},
		}
	}
</script>

<style lang="scss" scoped>
.account{
	position: relative;
	width: 100%;
	height: 100vh;
	.title{
		height: 33px;
		margin-top: 40rpx;
		color: rgba(51, 53, 56, 1);
		font-size: 24px;
		text-align: center;
	}
	.phone{
		height: 25px;
		margin: 142rpx 0 76rpx;
		color: rgba(51, 53, 56, 1);
		font-size: 18px;
		text-align: center;
	}
	.content{
		width: 86%;
		margin: 0 auto;
		.content-list{
			.content-item{
				display: flex;
				justify-content: space-between;
				align-items: center;
				text-align: right;
				height: 88rpx;
				border-bottom: 1px solid #eee;
				.item-title{
					color: rgba(50, 50, 51, 1);
					font-size: 14px;
				}
				.item-input{
					color: rgba(150, 151, 153, 1);
					font-size: 14px;
				}
				.item-code{
					color: rgba(49, 115, 255, 1);
					font-size: 14px;
				}
			}
		}
		.code{
			display: flex;
			justify-content: space-between;
			align-items: center;
			text-align: right;
			height: 88rpx;
			border-bottom: 1px solid #eee;
			.code-title{
				color: rgba(50, 50, 51, 1);
				font-size: 14px;
			}
			.code-right{
				display: inherit;
				.code-input{
					color: rgba(150, 151, 153, 1);
					font-size: 14px;
				}
				.code-num{
					margin-left: 36rpx;
					color: rgba(49, 115, 255, 1);
					font-size: 14px;
				}
			}
		}
		.btn{
			width: 90%;
			height: 88rpx;
			line-height: 88rpx;
			margin: 200rpx auto 0;
			border-radius: 2px;
			background-color: rgba(25, 137, 250, 1);
			color: rgba(255, 255, 255, 1);
			font-size: 32rpx;
		}
	}
	.bottom{
		position: absolute;
		height: 25px;
		width: 144rpx;
		left: 50%;
		bottom: 140rpx;
		margin-left: -72rpx;
		color: rgba(255, 96, 96, 1);
		font-size: 18px;
	}
}
</style>
