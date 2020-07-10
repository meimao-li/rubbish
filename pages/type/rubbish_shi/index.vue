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
						<text class="text1">湿垃圾</text>
						<view class="text_name1">
							<text class="text2">即易腐垃圾，易腐生物质生活废弃物</text>
							<image src="../../../static/classify/rubbish_shi/shi1.png" mode="" class="dry_refuse_img"></image>
						</view>
					</view>
					
					<!-- 干垃圾要求-->
					<view class="ask">
						<view class="text_name2">
							<text class="radius">1</text>
							<text class="ask1">投放前尽量沥干水分</text>
						</view>
						<view class="text_name2">
							<text class="radius">2</text>
							<text class="ask1">有外包装的应去除外包装</text>
						</view>
						<view class="text_name2">
							<text class="radius">3</text>
							<text class="ask1">纯流质的实物垃圾，如牛奶等，应直接倒入下水口</text>
						</view>		
						<view class="text_name2">
							<text class="radius">4</text>
							<text class="ask1">与其他种类垃圾分开投放</text>
						</view>		
					</view>
					
					
					<!-- 图片内容 -->
					<view class="main-classify">
						<view class="classifys">
							<image src="../../../static/classify/rubbish_shi/vegetables.png" class="classify-img" mode=""></image>
								<view class="classify-size">
									<text class="classify1">蔬菜</text>
								</view>
						</view>
						<view class="classifys">
						  <image src="../../../static/classify/rubbish_shi/fruits.png" class="classify-img" mode=""></image>
								<view class="classify-size">
									<text class="classify1">水果</text>
								</view>
						</view>
						<view class="classifys">
							<image src="../../../static/classify/rubbish_shi/meat.png" class="classify-img" mode=""></image>
								<view class="classify-size">
									<text class="classify2">肉类</text>
								</view>
						</view>
						<view class="classifys">
						  <image src="../../../static/classify/rubbish_shi/egg.png" class="classify-img" mode=""></image>
								<view class="classify-size">
									<text class="classify2">鸡蛋</text>
								</view>
						</view>
					</view>
					
					<!-- 图片内容 -->
					<view class="main-classify">
						<view class="classifys">
							<image src="../../../static/classify/rubbish_shi/expired.png" class="classify-img" mode=""></image>
								<view class="classify-size">
									<text class="classify3">过期食品</text>
								</view>
						</view>
						<view class="classifys">
						  <image src="../../../static/classify/rubbish_shi/ort.png" class="classify-img" mode=""></image>
								<view class="classify-size">
									<text class="classify3">剩饭剩菜</text>
								</view>
						</view>
						<view class="classifys">
							<image src="../../../static/classify/rubbish_shi/pluck.png" class="classify-img" mode=""></image>
								<view class="classify-size">
									<text class="classify4">动物内脏</text>
								</view>
						</view>
						<view class="classifys">
						  <image src="../../../static/classify/rubbish_shi/bread.png" class="classify-img" mode=""></image>
								<view class="classify-size">
									<text class="classify4">面包类</text>
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
					name:'剩饭剩菜'
				},{
					name:'瓜果果壳'
				},{
					name:'花卉植物'
				},{
					name:'过期食品'
				},{
					name:'橙子皮'
				},{
					name:'葱'
				},{
					name:'饼干'
				},{
					name:'番茄酱'
				},{
					name:'宠物饲料'
				},{
					name:'蛋壳'
				},{
					name:'西瓜皮'
				},{
					name:'马铃薯'
				},{
					name:'鱼骨'
				},{
					name:'葡萄干'
				},{
					name:'甘蔗'
				},{
					name:'玉米'
				},{
					name:'骨头'
				},{
					name:'虾皮'
				},{
					name:'蛋糕'
				} ,{
					name:'面包'
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
		border: #4682B4 1px dashed;
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
		background-color: #4682B4;
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
		border: #4682B4 1px dashed;
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
	.text2{
		margin-left: 30upx;
		font-size: 32upx;
		letter-spacing: 2upx;
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
		background-color: #4682B4;
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
		  margin-left: 25upx;
		font-size: 26upx;
	}
	.classify2{
		margin-left: 15upx;
		font-size: 26upx;
	}
	.classify3{
		margin-right: 30upx;
		font-size: 26upx;
	}
	.classify4{
		 
		font-size: 26upx;
	}
	 
</style>
