<template>
	<view class="content">
		 <view class="map-wrap">
			 <map markers="true"
			 scale="10" :latitude="latitude" 
			 :longitude="longitude" :markers="covers">
			 </map>
			 <cover-view class="icon-main"></cover-view>
		 </view>
		
	</view>
</template>

<script>
	export default{
		data(){
			return{
				longitude:118.803572,
				latitude:32.077625,
			}
		},
		onLoad(){ 
			
		},
		methods:{
			
		}
	}
	
</script>
<style>
</style>
<style scoped>
	.icon-main{
		left: 614rpx;
		top: 63rpx;
		position: absolute;
		z-index: 99;
		width: 90rpx; 
		height: 90rpx;
		box-shadow: 0px 1px 4px 0px rgba(203, 203, 203, 0.5);
		background-color: white;
		border-radius: 50%;
	}
	.icon-main image{
		width: 100%;
		height: 100%;
	}
	.map-wrap{
		position: relative;
		width: 100%;
		height: 100%;
	}
	map{
		width: 100vw;
		height: 100vh;
	}
</style>
