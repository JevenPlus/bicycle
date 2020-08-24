<template>
	<view>
		 <homeSearch></homeSearch>
		 <map></map>
		 <cover-view class="icon-position same-style"></cover-view>
		  <cover-view class="icon-more same-style"></cover-view>
		  <cover-view class="icon-weigui same-style"></cover-view>
		  <cover-view class="icon-kefu same-style"></cover-view>
		  <cover-view class="icon-usebike ">立即用车</cover-view>
	</view>
</template>
 
<script>
	import {map} from './map/index.vue'
	import {homeSearch} from './home-search/index.vue'
	export default{
		data(){
			return{}
		},
		components:{
			homeSearch,
			map
		}
	}
</script>

<style scoped>
	.same-style{
		position: absolute;
		z-index: 99;
		width: 90rpx; 
		height: 90rpx;
		box-shadow: 0px 1px 4px 0px rgba(203, 203, 203, 0.5);
		background-color: white;
		border-radius: 50%;
	}
	.icon-usebike{
		display: flex;
		justify-content: center;
		align-items: center;
		color: #FFFFFF;
		right: 265rpx;
		bottom: 13%;
		position: absolute;
		z-index: 99;
		width: 220rpx; 
		height: 220rpx;
		box-shadow: 0px 2px 6px -1px rgba(0, 0, 0, 0.14);
		background-color: rgba(12, 59, 158, 1);
		border-radius: 50%;
	}
	.icon-kefu{
		right: 42rpx;
		bottom: 13%;
	}
	.icon-weigui{
		right: 42rpx;
		bottom: 23%;	
	}
	.icon-more{
		left: 42rpx;
		bottom: 23%;	
	}
	.icon-position{
		left: 42rpx;
		bottom: 13%;		
	}
</style>
