<template>
	<view class="sreach-wrap">
		<view class="search-input">
			<input placeholder="搜索目的地"></input>
			<view class="search-icon iconfont icon-sousuo" >
			</view>
		</view>
	</view>
</template>
 
<script>
</script>

<style scoped>
	.sreach-wrap{
		position: relative;
		width: 675rpx;
		height: 97rpx;
		margin: 0 40rpx;
		display: flex;
		align-items: center;
		justify-content: center;
	}
	.search-icon{
		position: fixed;
		left: 290rpx;
		top: 34rpx; 
		color: #969799;
	}
	.search-input input{
		padding-left: 17rpx;
		color: #C8C9CC;
		text-align: center;
		font-size: 25rpx;
		width: 618rpx;
		height: 61rpx;
		background-color: #F7F8FA;
		border-radius: 180rpx;
	}
</style>
