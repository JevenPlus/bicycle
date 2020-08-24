<template>
	<view class="content">
		<homeSearch></homeSearch>
		<cover-view class="map-wrap">
			<map></map>
			<cover-view class="bikedetail-wrap">
				<cover-view class="bikedetail-title">
					<cover-view class="bikedetail-name">车辆详情</cover-view>
					<cover-view class="bikedetail-rule">计费规则</cover-view>
				</cover-view>
				<cover-view class="bikedetail-num">YL112544515</cover-view>
				<cover-view class="bikedetail-status">
					<cover-view class="status-container" v-for="(item,index) in statusInfo" :key="index">
						<cover-view class="status-title">{{item.title}}</cover-view>
						<cover-view class="status-content">{{item.content}}</cover-view>
					</cover-view>
				</cover-view>
				<cover-view class="bikedetail-feedback">
					<cover-view class="feedback-item" v-for="(item1,index1) in feedbackInfo" :key="index1">
						<cover-view class="status-title">{{item1.title}}</cover-view>
						<cover-view class="item-img">
							<cover-image :src="item1.img"></cover-image>
						</cover-view>
					</cover-view>
				</cover-view>
				<cover-view class="bottom-boder"></cover-view>
				<cover-view class="bottom-tool">
					<cover-view class="tool-left">预约用车</cover-view>
					<cover-view class="tool-right">立即开锁</cover-view>
				</cover-view>
			</cover-view>
		</cover-view>
	</view>
</template>

<script>
	import {
		map
	} from '../home/map/index.vue'
	import {
		homeSearch
	} from '../home/home-search/index.vue'
	export default {
		data() {
			return {
				statusInfo: [{
						title: '剩余电量',
						content: '46%'
					},
					{
						title: '预估续航',
						content: '36KM'
					},
					{
						title: '距目的地',
						content: '未设置'
					},
				],
				feedbackInfo: [{
						title: '车辆保修',
						img: '../../static/3.png'
					},
					{
						title: '违停举报',
						img: '../../static/4.png'
					},
					{
						title: '寻车铃',
						img: '../../static/5.png'
					},
				],
				longitude: 118.803572,
				latitude: 32.077625,
			}
		},
		components: {
			homeSearch,
			map
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>
<style>
</style>
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
	.bottom-boder{
		margin: 0 54rpx;
		opacity: 0.15;
		border: 1rpx solid rgba(161, 170, 188, 1);
	}
	//车辆反馈
	.bikedetail-feedback {
		display: flex;
		margin: 0 43rpx;

		.feedback-item {
			&:nth-child(2) {
				margin: 0 132rpx;
			}
			&:nth-child(3) {
				margin-left: 13rpx;
			}
			display: flex;
			flex-direction: column;
			align-items: center;
			.status-title {
				color: #949494;
				font-size: 25rpx;
				font-family: PingFangSC-Medium;
			}
			.item-img {
				margin-top: 24rpx;
				width: 63rpx;
				height: 63rpx;
				margin-bottom: 45rpx;
				cover-image {
					text-align: center;
					width: 100%;
					height: 100%;
				}
			}
		}
	}

	//车辆状态
	.bikedetail-status {
		display: flex;
		margin: 0 43rpx;
		margin-bottom: 56rpx;

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

	//车辆编号
	.bikedetail-num {
		font-size: 33rpx;
		color: #A5A5A5;
		font-family: Futura-Medium;
		margin-left: 43rpx;
		margin-bottom: 38rpx;
	}

	//车辆详情
	.bikedetail-title {
		display: flex;
		justify-content: space-between;
		align-items: center;
		padding: 0 43rpx;
		margin-top: 47rpx;
		margin-bottom: 43rpx;

		.bikedetail-name {
			font-weight: bold;
			color: rgba(51, 53, 56, 1);
			;
			font-size: 43rpx;
			font-family: PingFangSC-Medium;
		}

		.bikedetail-rule {
			color: $color;
			font-size: 25rpx;
			font-family: PingFangSC-Medium;
		}
	}

	.bikedetail-wrap {
		overflow: hidden;
		position: absolute;
		z-index: 99;
		left: 47rpx;
		bottom: 10%;
		width: 652rpx;
		height: 655rpx;
		background-color: #FFFFFF;
		border-radius: 18rpx;
	}
	.map-wrap {
		position: relative;
		width: 100%;
		height: 100%;
	}
	map {
		width: 100vw;
		height: 100vh;
	}
</style>
