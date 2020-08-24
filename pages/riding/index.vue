<template>
	<view class="content">
		<map></map>
		<cover-view class="riding-wrap">
			<cover-view class="riding-title">
				<cover-view class="riding-name">骑行中</cover-view>
				<cover-view class="riding-rule">更多功能</cover-view>
			</cover-view>
			<cover-view class="riding-num">YL112544515</cover-view>
			<cover-view class="riding-status">
				<cover-view class="status-container" v-for="(item,index) in ridingInfo" :key="index">
					<cover-view class="status-title">{{item.title}}</cover-view>
					<cover-view class="status-content">{{item.content}}</cover-view>
				</cover-view>
			</cover-view>
			<cover-view class="bottom-boder"></cover-view>
			<cover-view class="bottom-tool">
				<cover-view class="tool-left">预约用车</cover-view>
				<cover-view class="tool-right">立即开锁</cover-view>
			</cover-view>
		</cover-view>
	</view>
</template>

<script>
	import {map} from '../home/map/index.vue'
	export default{
		data(){
			return{
				ridingInfo: [{
						title: '骑行时间',
						content: '10\'20\'\''
					},
					{
						title: '骑行距离',
						content: '3KM'
					},
					{
						title: '距目的地',
						content: '1.4KM'
					},
				],
			}
		},
		components:{
			map
		}
	}
</script>

<style scoped lang="scss">
	//底部工具
	.bottom-tool{
		margin: 0 110rpx;
		display: flex;
		margin-top: 51rpx;
		justify-content: space-between;
		.tool-left{
			font-size: 32rpx;
			color: $color;
		}
		.tool-right{
			font-size: 32rpx;
			color: $color;
			font-weight: bold;
		}
	}
	//分割线
	.bottom-boder{
		margin: 0 54rpx;
		opacity: 0.15;
		border: 1rpx solid rgba(161, 170, 188, 1);
	}
	//骑行状态
	.riding-status {
		display: flex;
		margin: 0 43rpx;
		margin-bottom: 51rpx;
		.status-container {
			&:nth-child(2) {
				margin: 0 132rpx;
			}
			.status-title {
				color: #949494;
				font-size: 25rpx;
				font-family: PingFangSC-Medium;
			}
			.status-content {
				color: #383838;
				font-size: 32rpx;
				font-family: Futura-Medium;
				text-align: center;
				margin-top: 15rpx;
			}
		}
	}
	//编号
	.riding-num {
		font-size: 33rpx;
		color: #A5A5A5;
		font-family: Futura-Medium;
		margin-left: 43rpx;
		margin-bottom: 38rpx;
	}
	
	//骑行中
	.riding-title {
		display: flex;
		justify-content: space-between;
		align-items: center;
		padding: 0 43rpx;
		margin-top: 47rpx;
		margin-bottom: 43rpx;
	
		.riding-name {
			font-weight: bold;
			color: rgba(51, 53, 56, 1);
			;
			font-size: 43rpx;
			font-family: PingFangSC-Medium;
		}
		.riding-rule {
			color: $color;
			font-size: 25rpx;
			font-family: PingFangSC-Medium;
		}
	}
	//外容器
	.riding-wrap {
		position: absolute;
		z-index: 99;
		left: 47rpx;
		bottom: 51rpx;
		width: 652rpx;
		height: 484rpx;
		background-color: #FFFFFF;
		border-radius: 18rpx;
	}
	.hha{
		position: fixed;
		z-index: 99;
		left: 50rpx;
		top: 60rpx;
	}
</style>
