<template>
	<view :animation="animationData">
		<!-- 序号 -->
		<view class="xuhao">
			  <view class="number_color">{{index}}</view>
				<view class="number_color2"> / 10</view>
		</view>
		
		<!-- 问题 -->
		<view class="question">
			<view class="view-title">
				 <text id="info">{{rubbish}}</text>
			</view>
		</view>
		<!-- 选项图片 -->
		<view class="question-img">
				<view class="main-classify">
					 <view @click="switchTabToClassify(0)">
						 <view class="clickAnswer">
						 	  <text class="answer_text">干垃圾</text>
						 </view>
					 </view>
				</view>
				 
				<view class="main-classify">
					 <view @click="switchTabToClassify(1)">
						 <view class="clickAnswer">
						 	  <text class="answer_text">湿垃圾</text>
						 </view>
					 </view>
				</view>
				
				<view class="main-classify">
					 <view @click="switchTabToClassify(2)">
						 <view class="clickAnswer">
						 	  <text class="answer_text">可回收物</text>
						 </view>
					 </view>
				</view>
				
				<view class="main-classify" >
					<view  @click="switchTabToClassify(3)">
							<view class="clickAnswer">
								  <text class="answer_text">有害垃圾</text>
							</view>
					</view>
			  </view>
		</view>
		
	</view>
</template>

<script>
	let questions = [
		{
			id:1,
			name:'干电池',
			type:0,
			classify:'干垃圾'
		},
		{
			id:2,
			name:'西瓜',
			type:1,
			classify:'湿垃圾'
		},
		{
			id:3,
			name:'塑料瓶',
			type:2,
			classify:'可回收物'
		},
		{
			id:4,
			name:'有汞电池',
			type:3,
			classify:'有害垃圾'
		},
		{
			id:5,
			name:'废纸',
			type:0,
			classify:'干垃圾'
		},
		{
			id:6,
			name:'土豆',
			type:1,
			classify:'湿垃圾'
		},
		{
			id:7,
			name:'易拉罐',
			type:2,
			classify:'可回收物'
		},
		{
			id:8,
			name:'荧光棒',
			type:3,
			classify:'有害垃圾'
		},
		{
			id:9,
			name:'糖果',
			type:1,
			classify:'湿垃圾'
		},
		{
			id:10,
			name:'镜子',
			type:2,
			classify:'可回收物'
		},
		{
			id:11,
			name:'过期药品',
			type:3,
			classify:'有害垃圾'
		},
		{
			id:12,
			name:'树叶',
			type:1,
			classify:'湿垃圾'
		},
		{
			id:13,
			name:'纸巾',
			type:2,
			classify:'可回收物'
		},
		{
			id:14,
			name:'面包',
			type:1,
			classify:'湿垃圾'
		}
	];
	export default {
		data() {
			return {
				index:0,
				scores:0,
				rubbish:'干电池',
				current:0,//随机生成的值
				animationData:{
					//动画
				},
				problems:[]
			}
		},
		onLoad() {
			
		},
		
		onShow(){
			this.index = 1;
			getApp().globalData.totalScore = 0;
			//页面加载完之后随机生成1道题
			//this.current = Math.round(Math.random()*questions.length);
			
			//利用set不能重复往里面放
			//取元素
			  let set = new Set();
				while(set.size<10){
					set.add(Math.round(Math.random()*questions.length));
				}
				
				for(let i of set){
					this.problems.push(questions[i]);
				}
				
				this.rubbish = this.problems[this.index-1].name;
			 
		},
		methods: {
			//动画效果
			donghua() {
					var animation = uni.createAnimation({
						duration: 5000,//切换的时间
						timingFunction: 'ease',//擦屏效果
					})
					this.animation = animation
					animation.opacity(0).translate(-300).step()
					this.animationData = animation.export()
					
					setTimeout(function() {
						animation.translate(10).opacity(0.5).step({
							duration: 0
						})
						this.animationData = animation.export()
					}.bind(this), 400);
					setTimeout(function() {
						animation.translate(0).opacity(1).step({
							duration: 800
						})
						this.animationData = animation.export()
						
					}.bind(this), 500);
					
				},
			
			switchTabToClassify(answer){
				if(this.index-1>10){
					//统计成绩
					getApp().globalData.totalScore = this.scores;
					let score = "恭喜您"+"，答对了"+this.scores+"道题";
					uni.showModal({
						title:"恭喜您",
						content:score,
						confirmText:'确定',
						showCancel:false,
						 
						success:function(res){
							uni.switchTab({
								//跳转到首页
								url:"../index/index"
							})
							 
						}
					});
					return;
				}
				
				let that = this;
				let yourAnswer = '';
				let rubbish = this.problems[this.index-1];
				let rightAnswer = this.rubbish + "属于" +rubbish.classify;
				if(answer===rubbish.type){
				
				  this.scores++;
					//动画
					this.donghua();
					
				}else{
					if(answer===0){
						yourAnswer = '干垃圾';
					}else if(answer===1){
						yourAnswer = '湿垃圾';
					}else if(answer===2){
						yourAnswer = '有害垃圾';
					}else if(answer===3){
						yourAnswer = '可回收物';
					}
					
					
					uni.showModal({
						title:"您选错了",
						content:rightAnswer,
						confirmText:'知道了',
						showCancel:false,
						//进行下一道题
						success:function(res){
							//动画
							that.donghua();
							 
						}
					});
				}
				//进行下一道题
				
				this.index++;
				if(this.index<=9){
									
					this.rubbish = this.problems[this.index-1].name;
				}
			}
		}
	}
</script>

<style>
	.question{
		padding: 20upx;
	}
	#info{
		
		font-size:50upx;
	}
	.view-title{
		display: flex;
		justify-content: center;
		align-items: center;
		
		margin-top: 10upx;
	}
	.view-title2{
		display: flex;
		justify-content: center;
		align-items: center;
		color: #DD524D;
		font-size: 22upx;
		margin-top: 8upx;
	}
	
	.main-classify{
		display: flex;
		justify-content: center;
		direction: center;/*居中的方向  */
		 
	}
	 
	.xuhao{ 
		display: flex;
		 justify-content: flex-start; 
		margin-top: 10upx;
		padding: 30upx;
		 
	}
	.number_color{
		color: #FFC125;
		
	}
	.number_color2{
		color: #C0C0C0;
	}
	
	.clickAnswer{
		width: 460upx;
		height: 80upx;
		border-radius: 65upx;
		border: #808080 1px solid;
		margin-top: 50upx;
	}
	.answer_text{
		display: flex;
		justify-content: center;
		 margin-top: 20upx;
		text-align: center;
	}
</style>
