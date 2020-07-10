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
						<text class="text1">可回收物</text>
						<view class="text_name1">
							<text class="text2">指事宜回收可循环利用的废弃物</text>
							<image src="../../../static/classify/rubbish_khs/khs1.png" mode="" class="dry_refuse_img"></image>
						</view>
					</view>
					
					<!-- 干垃圾要求-->
					<view class="ask">
						<view class="text_name2">
							<text class="radius">1</text>
							<text class="ask1">投放时应尽量保持清洁干燥，避免污染</text>
						</view>
						<view class="text_name2">
							<text class="radius">2</text>
							<text class="ask1">有内容物的，应清空并清洁后压扁投放</text>
						</view>
						<view class="text_name2">
							<text class="radius">3</text>
							<text class="ask1">易碎尖锐的，应包裹后投放</text>
						</view>			 
					</view>
					
					
					<!-- 图片内容 -->
					<view class="main-classify">
						<view class="classifys">
							<image src="../../../static/classify/rubbish_khs/book.png" class="classify-img" mode=""></image>
								<view class="classify-size">
									<text class="classify1">书本报纸</text>
								</view>
						</view>
						<view class="classifys">
						  <image src="../../../static/classify/rubbish_khs/wastebasket.png" class="classify-img" mode=""></image>
								<view class="classify-size">
									<text class="classify1">废纸箱</text>
								</view>
						</view>
						<view class="classifys">
							<image src="../../../static/classify/rubbish_khs/toy.png" class="classify-img" mode=""></image>
								<view class="classify-size">
									<text class="classify2">塑料玩具</text>
								</view>
						</view>
						<view class="classifys">
						  <image src="../../../static/classify/rubbish_khs/bottle.png" class="classify-img" mode=""></image>
								<view class="classify-size">
									<text class="classify2">塑料瓶</text>
								</view>
						</view>
					</view>
					
					<!-- 图片内容 -->
					<view class="main-classify">
						<view class="classifys">
							<image src="../../../static/classify/rubbish_khs/ring-pull.png" class="classify-img" mode=""></image>
								<view class="classify-size">
									<text class="classify3">易拉罐</text>
								</view>
						</view>
						<view class="classifys">
						  <image src="../../../static/classify/rubbish_khs/parts.png" class="classify-img" mode=""></image>
								<view class="classify-size">
									<text class="classify3">金属零件</text>
								</view>
						</view>
						<view class="classifys">
							<image src="../../../static/classify/rubbish_khs/electronics.png" class="classify-img" mode=""></image>
								<view class="classify-size">
									<text class="classify4">电子产品</text>
								</view>
						</view>
						<view class="classifys">
						  <image src="../../../static/classify/rubbish_khs/plush.png" class="classify-img" mode=""></image>
								<view class="classify-size">
									<text class="classify4">毛绒制品</text>
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
					name:'易拉罐'
				},{
					name:'饮料瓶'
				},{
					name:'洗发水瓶'
				},{
					name:'书本'
				},{
					name:'纸板箱'
				},{
					name:'书本'
				},{
					name:'旧衣物'
				},{
					name:'玻璃杯'
				},{
					name:'食品罐头'
				},{
					name:'旧书包'
				},{
					name:'旧鞋子'
				},{
					name:'牛奶盒'
				},{
					name:'旧玩偶'
				},{
					name:'旧床上用品'
				},{
					name:'玻璃壶'
				},{
					name:'旧铁锅'
				},{
					name:'打印机'
				},{
					name:'复印机'
				}
				
				]
			}
		}		
	}			
</script>

<style>
	.na{
		
		padding: 30upx;
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
		border: #7CCD7C 1px dashed;
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
		background-color: #7CCD7C;
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
		border: #7CCD7C 1px dashed;
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
		background-color: #7CCD7C;
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
		margin-left: 25upx;
		font-size: 26upx;
	}
	.classify4{
		 
		font-size: 26upx;
	}
	
</style>
