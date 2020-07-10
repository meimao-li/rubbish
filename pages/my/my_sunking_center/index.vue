<template>
	<view class="discover">
	 
		
		<!-- 分段器 -->
		<view class="tab">
			<uni-segmented-control :current="current"
			 :values="items.map(v => v.title)"
							@clickItem="onClickItem" 
							style-type="text"
							active-color="#FFD700"
							class="segmented">
			</uni-segmented-control>
		</view>
		
		<!-- 显示不同的分组件，取决于当前的current的值-->
		<view>
			 <view v-if="current==0">
				 <New></New>
			 </view>
			 
			 <view v-if="current==1">
				 <SunkingCenter></SunkingCenter>
			 </view>
			 <view v-if="current==2">
				 <Comment></Comment>
			 </view>
			 
			 
		</view>
		
	</view>
</template>

<script>
	//导入子组件
	import New from "./new/index.vue"
	import SunkingCenter from "./comment/index.vue"
	import Comment from "./popularoty/index.vue"
 
	
	
	//分段器
	import {uniSegmentedControl} from '@dcloudio/uni-ui'
	
	export default {
		data() {
			return {
				items:[
					{title:'最新晒单'},
					{title:'人气晒单'},
					{title:'评论最多'},
					 
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
			New,
			SunkingCenter,
			Comment,
			 
			uniSegmentedControl
			
		}
	}
</script>

<style>
	 
	.tab{
		margin-top: 50upx;
	}
	.segmented{
		
	}
</style>

