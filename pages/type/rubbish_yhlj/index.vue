<template>
	<view class="dry_refuse">
		 
		
	<!-- 	<view class="explain">
				<view class="main-classify1"> 
					 <view class="clickAnswers">
							<text class="text1">干垃圾</text>
					 </view>
				</view> -->
				 
				<!-- <view class="main-classify"> 
					 <view class="clickAnswer">
							<text class="answer_text2">除其它三类垃圾外的生活废弃物</text>
					 </view> 
				</view> -->
				
				<!-- <view class="main-classify2"> 
					 <view class="clickAnswer">
							<image src="../../../static/分类/干垃圾/干垃圾图标.png" mode="" class="dry_refuse_img"></image>
					 </view> 
				</view> -->
		<!-- 外边框 -->
 	  <view class="explain">
			 <view class="main-classify1">
					<!-- 干垃圾定义 -->
					<view class="map">
						<text class="text1">有害垃圾</text>
						<view class="text_name1">
							<text class="text2">指对人体健康或自然环境造成直接或潜在危害的废弃物</text>
							<image src="../../../static/classify/rubbish_yh/yh1.png" mode="" class="dry_refuse_img"></image>
						</view>
					</view>
					
					<!-- 干垃圾要求-->
					<view class="ask">
						<view class="text_name2">
							<text class="radius">1</text>
							<text class="ask1">分类投放有害垃圾时，应注意轻放</text>
						</view>
						<view class="text_name2">
							<text class="radius">2</text>
							<text class="ask1">易碎尖锐的，应连带包装或包裹后投放</text>
						</view>
						<view class="text_name2">
							<text class="radius">3</text>
							<text class="ask1">压力罐装容器，应排空内容物后投放</text>
						</view>			 
					</view>
					
					
					<!-- 图片内容 -->
					<view class="main-classify">
						<view class="classifys">
							<image src="../../../static/classify/rubbish_yh/batteries.png" class="classify-img" mode=""></image>
								<view class="classify-size">
									<text class="classify1">废电池</text>
								</view>
						</view>
						<view class="classifys">
						  <image src="../../../static/classify/rubbish_yh/halide.png" class="classify-img" mode=""></image>
								<view class="classify-size">
									<text class="classify1">卤素灯</text>
								</view>
						</view>
						<view class="classifys">
							<image src="../../../static/classify/rubbish_yh/fluorescent.png" class="classify-img" mode=""></image>
								<view class="classify-size">
									<text class="classify2">荧光灯</text>
								</view>
						</view>
						<view class="classifys">
						  <image src="../../../static/classify/rubbish_yh/polish.png" class="classify-img" mode=""></image>
								<view class="classify-size">
									<text class="classify2">指甲油</text>
								</view>
						</view>
					</view>
					
					<!-- 图片内容 -->
					<view class="main-classify">
						<view class="classifys">
							<image src="../../../static/classify/rubbish_yh/insecticide.png" class="classify-img" mode=""></image>
								<view class="classify-size">
									<text class="classify3">杀虫剂</text>
								</view>
						</view>
						<view class="classifys">
						  <image src="../../../static/classify/rubbish_yh/ray_film.png" class="classify-img" mode=""></image>
								<view class="classify-size">
									<text class="classifyX">X光片</text>
								</view>
						</view>
<!-- 						<view class="classifys">
							<image src="../../../static/classify/rubbish_yh/axpired_medicines.png" class="classify-img" mode=""></image>
								<view class="classify-size">
									<text class="classify4">过期药品</text>
								</view>
						</view> -->
						<view class="classifys">
						  <image src="../../../static/classify/rubbish_yh/thermometer.png" class="classify-img" mode=""></image>
								<view class="classify-size">
									<text class="classify4">温度计</text>
								</view>
						</view>
					</view>
			 </view>
		</view>
		
		<view class="common_items">
			<view class="common_items_text">常见物品</view>
		</view>
		
		
		<view class="items">
			<view class="item_names">
				<text v-for="item in items" class="na">{{item.name}}</text>
			</view>
		</view>
		
		<!-- 占位 -->
		<view class="null"></view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				items:[{
					name:'废电池'
				},{
					name:'温度计'
				},{
					name:'过期药品'
				},{
					name:'油漆桶'
				},{
					name:'油漆'
				},{
					name:'废药品'
				},{
					name:'杀虫剂'
				},{
					name:'打火机'
				},{
					name:'创口贴'
				},{
					name:'调色板'
				},{
					name:'酒精'
				},{
					name:'水彩笔'
				},{
					name:'农药瓶'
				},{
					name:'口服液瓶'
				},{
					name:'废灯管'
				},{
					name:'香水瓶'
				},{
					name:'过期化妆品'
				} 
				]
			}
		}		
	}			
</script>

<style>
	.na{
		
		padding: 17upx;
	  flex-wrap:wrap;
		justify-content:space-around;
	}
	.null{
		height: 200upx;
	}
	.items{
		width:90%;
		height: 300upx;
		border-radius: 14upx;
		border: #CD6839 1px dashed;
		margin: 0px auto;
		margin-top: 40upx;
		display: flex;
	
		
	}
	.item_names{
		padding:28upx;


	}
	.common_items{
		height:70upx;
		width: 190upx;
		margin-top: 40upx;
		border-radius: 14upx;
		background-color: #CD6839;
		display: flex;
		justify-content: center;
		margin-left: 36upx;
		
	}
	.common_items_text{
		color: #FFFFFF;
		font-size: 30upx;
		letter-spacing: 4upx;
		justify-content: center;
		 margin-top: 15upx;
	}
	.classify-img{
		width: 100upx;
		height: 80upx;
		
	}

.explain{
		width:90%;
		height: 800upx;
		border-radius: 14upx;
		border: #CD6839 1px dashed;
		display: flex;
		
	 flex-direction: row;
	 margin: 0px auto;
	 margin-top: 40upx;
		
	}
	.clickAnswer{
		display: flex;
		justify-content: flex-end;
	}
	.text1{
		display: flex;
		 letter-spacing: 3upx;
		font-size: 40upx;
		padding: 28upx;
	}
	/* 	.explain_text2{
		 height: 50upx;
		 width: 90%;
		float: left;
		
		 justify-content: flex-start; 
		padding: 30upx;
	}*/
	.text2{
		margin-left: 30upx;
		font-size: 32upx;
		letter-spacing: 3upx;
	}
  
 .main-classify2{ 
	 display: flex;
	 justify-content: flex-end;
 }
	.dry_refuse_img{
		width: 100upx;
		height: 100upx;
		float: right;
		display: flex;
		justify-content: flex-end;
		margin-left: 60upx;
		 
	}
	.ask{
		margin-top: 70upx;
	
	}
	.radius{ 
		width: 24upx;
		height: 24upx;
		border-radius: 14upx;
		background-color: #CD6839;
		color: #FFFFFF;
	}
	.ask1{
		font-size: 24upx;
		margin-left: 20upx;
	}
	.text_name2{
		margin-left: 30upx;
		font-size: 24upx;
		margin-top: 4upx;
	letter-spacing: 3upx;
	}
	.main-classify{
		display: flex;
		justify-content: center;
		direction: center;/* 居中的方向 */
		 margin-top: 66upx;
		 justify-content: space-around;
	}
	.classify-size{
		margin-top: 6upx;
		
	}
	.classify1{
		 margin-top: 6upx;
		font-size: 26upx;
	}
	.classify2{
		margin-left: 30upx;
		font-size: 26upx;
	}
	.classify3{
		
		font-size: 26upx;
	}
	.classify4{
		 
		font-size: 26upx;
	}
	.classifyX{
		margin-right: 16upx;
	}
</style>
