<template>
	<view class="home">
		<!-- 获取位置 -->
		<view class="map-view">
			<view class="location">
				<!-- 定位 -->
				<view class="map" @tap="getRegeo">
					<image src="../../static/guide/location.png" mode="" class="search-img"></image>
				</view>
				<!-- 城市 -->
				<view   class="city">
					 {{addressName}}
					 
				</view>
			</view>
			
			<!-- 搜索框 -->
			<view class="search">
				<!-- 关键词输入框 -->
				<view class="input-view-item">
					<input type="text" class="search-text" v-model="keyword" placeholder="请输入垃圾关键词" />
				</view>
				<view class="font-search" @tap="searchKeyWords">
					<image  src="../../static/guide/search.png" mode="" class="search-img"></image>
				</view>
			</view>
		</view>
		
		<!-- banner -->
		<!-- 轮播图 -->
		<swiper :indicator-dots="true" :autoplay="true" :interval="3000" :duration="1000">
			<swiper-item v-for="(item,index) in swipers" :key="index" class="swiper-flex">
				<view class="swiper-item">
					<image class="swiper-img" :src="item" mode=""></image>
				</view>
			</swiper-item>
		</swiper>
		
		<!-- 识别功能 -->
		<view class="distinguishs">
			<view class="distinguish">
				<!-- 语音识别 -->
				<view class="">
					<view class="voice" @touchstart="startRecord" @touchend="endRecord">
						<image src="../../static/guide/voice.png" mode="" class="img-size1"></image>
					</view>
				</view>
				
				<!-- 扫描识别 -->
				<view class="">
					<view class="scan">
						<image src="../../static/guide/scan.png" mode="" class="img-size"></image>
					</view>
				</view>
				
				<!-- 图片识别 -->
				<view class="">
					<view class="photo">
						<image src="../../static/guide/picture.png" mode="" class="img-size" @click="imgShiBie"></image>
					</view>
				</view>
			</view>
			<!-- 文字描述 -->
			<view class="fonts">
				<view class="font">
					语音识别
				</view>
				<view class="font">
					扫描识别
				</view>
				<view class="font">
					图片识别
				</view>
			</view>
		</view>
		
		<!-- 垃圾分类小常识 -->
		<view class="general_knowledge">
			<view class="xiao_knowledge">
				<b>垃圾分类小常识</b>
			</view>
			<view >
				<image src="../../static/guide/slideshow.png" mode="" class="knowledge_img"></image>
			</view>
		</view>
		
		<!-- 垃圾分类 -->
		<view class="rubbish_classify">
				<view class="xiao_knowledge">
					<b>垃圾分类</b>
				</view>
					<hr>
				<view >
					<view class="main-classify">
						<view class="classifys" @click="shi">
							<image src="../../static/guide/rubbish_shi.png" class="classify-img" mode=""></image>
								<view class="classify-size">
									<text class="text1">湿垃圾</text>
								</view>
						</view>
						<view class="classifys" @click="gan">
						  <image src="../../static/guide/rubbish_gan.png" class="classify-img" mode=""></image>
								<view class="classify-size">
									<text class="text2">干垃圾</text>
								</view>
						</view>
					</view>
					
					<view class="main-classify">
						<view class="classifys" @click="kehuishou">
							<image src="../../static/guide/rubbish_khs.png" class="classify-img" mode=""></image>
								<view class="classify-size">
									<text class="text3">可回收物</text>
								</view>
						</view>
						
						<view class="main-classify">
							<view class="classifys" @click="youhai">
								<image src="../../static/guide/rubbish_yh.png" class="classify-img" mode=""></image>
								<view class="classify-size">
									<text class="text4">有害垃圾</text>
								</view>
							</view>
				   	</view>
			    </view>
					
			</view>
		</view>
	</view>
	
</template>

<script>
	
	
	import amap from '../../common/amap-wx.js';  
	//录音管理器
	const recorderManager = uni.getRecorderManager();
	const innerAudioContext = uni.createInnerAudioContext();

	innerAudioContext.autoplay = true;
	export default {
		data() {
			
			return {
			 amapPlugin: null,  
			            key: 'cfb2818c304ad6ccf0ab98b195c3df20',  
			            addressName: '',  
			            weather: {  
			                hasData: false,  
			                data: []  
			            },
				vicePath:'',
				keyword:'干电池',
				swipers:[
					'../../static/guide/banner.png',
					'../../static/guide/1-.jpg',
					'../../static/guide/2-.jpg',
				]
				
			};
		},
		onLoad() {
			 this.amapPlugin = new amap.AMapWX({  
			            key: this.key  
			        });

			let self = this;
			recorderManager.onStop(function (res) {
				console.log('recorder stop' + JSON.stringify(res));
				let src = res.tempFilePath;
				//拿到数据之后开始发送http请求获取垃圾类型
				wx.uploadFile({
				  url: 'http://api.tianapi.com/txapi/voicelajifenlei/index ', //语音垃圾分类接口
				  method:'POST',
				  header:{
				  	'content-type':'multipart/form-data'
				  },
				  filePath: src,
				  name: 'say',
				  formData: {
				    key: '1e849019f2924e39afdaf14b4c3fba71',
				    format:'pcm'
				  },
				  success (res){
				    console.log(res.data)
				    wx.showModal({
				      title: '提示',
				      content: res.data,
				      showCancel: false
				    })
				  },
				  fail:function(res){
					  console.log(res.data)
					  wx.showModal({
					    title: '提示',
					    content: res.data,
					    showCancel: false
					  })
				  }
				})
			});
		},
		//定位
		
		//结束
		
		methods: {
			//定位开始
		     getRegeo() {  
				
		            uni.showLoading({  
		                title: '获取信息中'  
		            });  
		            this.amapPlugin.getRegeo({  
		                success: (data) =>{  
		                    console.log(data)
		                    this.addressName = data[0].regeocodeData.addressComponent.city;  
							/* console.log(this.addressName); */
							uni.hideLoading();
		                }  
		            });
				/* uni.navigateTo({
				 	url:'../ditu/index'
				 }) */
		        },
			//定位结束
			//关键词搜索开始
			searchKeyWords(){
				//发送异步请求，到我们的天行接口，查询当前垃圾垃圾类型
				this.request({
					url:'http://api.tianapi.com/txapi/lajifenlei/index?key=1e849019f2924e39afdaf14b4c3fba71&word='+this.keyword
				}).then(response=>{
					console.log(response);
					getApp().globalData.rubbishList = [];
					for (let rubbish of response.newslist) {
						let obj = {};
						//src
						if(rubbish.type==1){
							obj.src = '../../static/icos/ico-4.jpg';
						}else if(rubbish.type==3){
							obj.src = '../../static/icos/ico-1.jpg';
						}else if(rubbish.type==2){
							obj.src = '../../static/icos/ico-2.jpg';
						}else if(rubbish.type==0){
							obj.src = '../../static/icos/ico-3.jpg';
						}
						//title
						obj.title = rubbish.explain;
						obj.showText = true;
						obj.text = rubbish.name;
						getApp().globalData.rubbishList.push(obj);//将返回的数据添加到数组中，在页面中显示
						//getAPP().globalDate 把一个页面数据传输到另一个页面(全局变量)
						
						//跳转到详细页面
						uni.navigateTo({
							url:'../detail/index'
						})
					}
				}
				)
			},
			
			switchTabToClassify(current){
				getApp().globalData.current = current;
				
				uni.switchTab({
				    url: '/pages/type/index'
				});
			},
			//关键词搜索结束
			//语音部分方法开始
			 startRecord() {
				console.log('开始录音');
				recorderManager.start(
					{
					  duration: 20000,
					  numberOfChannels:2,
					  sampleRate:16000,
					  format: 'PCM'
					}
				);
			},
			endRecord() {
				console.log('录音结束');
				recorderManager.stop();
			},
			//语音部分方法结束
			//图像识别方法
			imgShiBie(){
				//获取图片  1）打开本地图片    2）拍照
				//base64编码
				//发送请求识别
				wx.chooseImage({
					count: 1, //1张图片，默认是9张
					sourceType:['album','camera'] ,//图片的打开方式   ，第一个是相册 ，第二个是相机拍照
					sizeType:['compressed'],     //压缩图片，提高速度
					success:function(result){ //打开成功之后，读取
						console.log(result);
						//读取图片，
						wx.getFileSystemManager().readFile({
							filePath:result.tempFilePaths[0],
							encoding:'base64',//指定读取文件的字符编码，如果不传，encoding ，则以ArrayBuffer，格式读取文件的二进制内容
							//读取成功
							success:res=>{ //ES6语法  
								//console.log('base64'+res.data);
								//拿到编码后开始发送图像识别接口
								wx.request({
									url:'http://api.tianapi.com/txapi/imglajifenlei/index ',
									method:'POST', //因为图片过大
									header:{ //请求头
										'content-type':'application/x-www-form-urlencoded'
									},
									data:{
										key:'1e849019f2924e39afdaf14b4c3fba71',//接口的key
										img:'data:image/png;base64,'+res.data,
										mode: 1
									},
									success:function(response){//成功之后
										console.log(response);
										getApp().globalData.rubbishList = [];//每遍历一次为空
										
										for (let rubbish of response.data.newslist) {
											let obj = {};//转换
											//处理图片
											if(rubbish.lajitype == 1){
												obj.src = '../../static/icos/ico-4.jpg';
											}else if(rubbish.lajitype == 3){
												obj.src = '../../static/icos/ico-1.jpg';
											}else if(rubbish.lajitype == 2){
												obj.src = '../../static/icos/ico-2.jpg';
											}else if(rubbish.lajitype == 0){
												obj.src = '../../static/icos/ico-3.jpg';
											}else if(rubbish.lajitype == 4){
												obj.src = '../../static/icos/share.png';
											}
											
											obj.title = rubbish.lajitip;//标题
											obj.showText = true ; 
											obj.text = rubbish.name;
											getApp().globalData.rubbishList.push(obj);//将返回的数据添加到数组中，在页面中显示
											//getAPP().globalDate 把一个页面数据传输到另一个页面(全局变量)
										
										}
										//跳转到详情页面
										uni.navigateTo({
											url:'../detail/index'
										});
									},
									
								});
								
							}
						});
					}
				})
			},
			 //跳转到干垃圾页面
			gan(){
				uni.navigateTo({
					url:'../type/rubbish_gan/index'
				})
			},
			//跳转到湿垃圾页面
			shi(){
				uni.navigateTo({
					url:'../type/rubbish_shi/index'
				})
			},
			//跳转到可回收页面
			kehuishou(){
				uni.navigateTo({
					url:'../type/rubbish_khs/index'
				})
			},
			//跳转到有害页面
			youhai(){
				uni.navigateTo({
					url:'../type/rubbish_yhlj/index'
				})
			},

		}
	}
</script>

<style>
	/* 搜索框 */
	
	/* .input-view-item{
		width: 100upx;
		align-items: center;
		padding: 8upx;
	}
	.search-text{
		width: 240upx;
		height: 80upx;
		text-align: center;
		font-size: 25upx;
	} */
	
	.map-view{
		display: flex;
		flex: 1;
	 justify-content: space-between;
		padding: 24upx;
	}
	/* 定位 */
	.location{
		display: flex;
		justify-content: flex-start;/* 左对齐 */
		margin-left: 20upx;
		 
	}
	.city{
		margin-left: 16upx;
		font-size: 36rpx;
		letter-spacing:5upx;
	}
	/* 搜索 */
	.search{
		display: flex;
		justify-content: center;/* 右对齐 */
		margin-right: 20upx;
	}
	
	.search-img{
		width: 42upx;
		height: 46upx;
	}
	
	.swiper-flex{
		display: flex;
		justify-content: center;
	}
	/* 修改轮播图高度 */
	swiper{
	  height: 500upx;
	}
	.swiper-img{
		width: 750upx;
		height: 500upx;
	}
	.indicator-dots{
		color: #007AFF;
	}
	
	/* 识别功能 */
	.distinguishs{
		width: 100%;
		height: 190upx;
		/* border: #007AFF 1rpx solid; */
		
	}
	.distinguish{
		margin-top: 35upx;
		display: flex;
		justify-content: space-around;/* 水平分布 */
	}
	.img-size{
		width: 80upx;
		height: 80upx;
		padding: 5upx;
	}
	.img-size1{
		width: 64upx;
		height: 89upx;
		padding: 1upx;
	}
	.fonts{
		
		display: flex;
		
		justify-content: space-around;/* 水平分布 */
	}
	.font{
		font-size: 28upx;
		color: #FFC125;
		
	}
	.general_knowledge{
		 padding: 20upx;
		
		height: 440upx;
		
	}
	.xiao_knowledge{
		font-size: 34rpx;
		padding: 10upx;
		letter-spacing:5upx;
		font-weight: bold;
		margin-left: 20upx;
		height: 50upx;
		
	}

	.knowledge_img{
		 display: flex;
		 justify-content: center;
		height: 360upx;
		width: 90%;
		flex-direction: row;
		margin: 0px auto;
		direction: row;
		align-items: center;
		 margin-top: 10upx;
	}
	.rubbish_classify{
		 padding: 20upx;
		margin-top: 10upx;
		height: 800upx;
		/* border: #4CD964 1rpx solid; */
	}
	.main-classify{
		display: flex;
		justify-content: center;
		direction: center;/* 居中的方向 */
		 
	}
	hr{
	 display: flex;
	 justify-content: space-between;
	   
	    
		margin-top:20upx;
		 border-top:1px solid #CCCCCC;
	}
	.classifys{
		padding:40upx;
	}
	
	.classify-img{
		width: 250upx;
		height: 220upx;
		
	}
	.classify-size{
		display: flex;
		justify-content: center;
		direction: center;/* 居中的方向 */
		margin-left: 66upx;
		 letter-spacing:5upx;/* 字体间隔 */
		 font-size: 30upx;
		  margin-top: 10upx;
	}
	.text1{
		color:#4682B4 ;
		font-weight: bold;
		font-size:30upx;
		
	}
	.text2{
		color:#C71585 ;
		font-weight: bold;
		font-size:30upx;
		
	}
	.text3{
		color:#7CCD7C ;
		font-weight: bold;
		font-size:30upx;
		
	}
	.text4{
		color:#CD6839 ;
		font-weight: bold;
		font-size:30upx;
		
	}
</style>
