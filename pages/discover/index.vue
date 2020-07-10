<template>
	<view class="discover">
		<!-- 标题 -->
		<view class="title">
			 <text class="title1">精选晒单</text>
			 <text class="title2">NEW</text>
		</view>
		<!-- 黑色 -->
		<view class="discover_img">
			<image src="../../static/find_page/Home.png" mode="" class="imgs"></image>
			<hr>
		</view>
		
		<!-- 分段器 -->
		<view class="tab">
			<uni-segmented-control :current="current"
			 :values="items.map(v => v.title)"
							@clickItem="onClickItem" 
							style-type="button"
							active-color="#FFD700"
							class="segmented">
			</uni-segmented-control>
		</view>
		
		<!-- 显示不同的分组件，取决于当前的current的值-->
		<view>
			 <view v-if="current==0">
				 <DiscoverAll></DiscoverAll>
			 </view>
			 
			 <view v-if="current==1">
				 <DiscoverRefuseBin></DiscoverRefuseBin>
			 </view>
			 <view v-if="current==2">
				 <DiscoverBookBox></DiscoverBookBox>
			 </view>
			 
			 <view v-if="current==3">
				 <DiscoverTableNumber></DiscoverTableNumber>
			 </view>
			 
			 <view v-if="current==4">
			 		
					<DiscoverBench></DiscoverBench>
			 </view>
			 
			 <view v-if="current==5">
				 <DiscoverLife></DiscoverLife>
			 		
			 </view>
		</view>
		
	</view>
</template>

<script>
	//导入子组件
	import DiscoverAll from "./discover_all/index.vue"
	import DiscoverBench from "./discover_bench/bench.vue"
	import DiscoverBookBox from "./discover_bookbox/index.vue"
	import DiscoverLife from "./discover_life/index.vue"
	import DiscoverRefuseBin from "./discover_ljt/index.vue"
	import DiscoverTableNumber from "./discover_tablenumber/index.vue"
	
	
	//分段器
	import {uniSegmentedControl} from '@dcloudio/uni-ui'
	
	export default {
		data() {
			return {
				items:[
					{title:'全部'},
					{title:'垃圾桶'},
					{title:'抽纸盒'},
					{title:'桌几'},
					{title:'板凳'},
					{title:'生活'},
				],
				current: 0
			}
		},
		onShow() {
			this.current = getApp().globalData.current;
		},
		onLoad() {
	
		},
		methods: {
			onClickItem(index) {
					if (this.current !== index.currentIndex) {
							this.current = index.currentIndex;
					}
			}
	
		},
		components:{
			
			DiscoverAll,
			DiscoverBench,
			DiscoverBookBox,
			DiscoverLife,
			DiscoverRefuseBin,
			DiscoverTableNumber,
			
			uniSegmentedControl
			
		}
	}
</script>

<style>
	.title{
	 
		display: flex;
		justify-content: flex-start;/* 左对齐 */
		margin-left: 20upx;
		 
	letter-spacing:5upx;
		flex: 1;
	  
		padding: 24upx;
	}
	.title1{
		margin-left: 16upx;
		font-size: 36rpx;
		letter-spacing:6upx;
		font-size: 40upx;
	}
	.title2{
		font-size: 20upx;
		color: #FFD700;
	}
	hr{
	 display: flex;
	 justify-content: space-between;
	   
	    
		
		 border-top:1px solid #CCCCCC;
	}
	.imgs{
		width: 167upx;
		height: 8upx;
		display: flex;
		margin-top: 6upx;
		justify-content: flex-start;/* 左对齐 */
		margin-left: 58upx;
	}
	.tab{
		margin-top: 50upx;
	}
	.segmented{
		
	}
</style>

