<template>
	<view class="center">
		<!-- <view class="center_top">
			<view class="mask"></view>
			<image :src="avatarUrl" mode="" class="mask"></image>
		</view> -->
		<view class="center_box_bg">
			<view class="profily">
				<view class="base">
					<!-- <view class="profily_header"></view> -->
					<image :src="avatarUrl" mode="" id="avatarUrl" @click="clickImg"></image>
					<text>{{nickname}}</text>
					<button v-if="nickname==='昵称'" type="default" open-type="getUserInfo" @getuserinfo="getUserInfo" id="buttonInfo" withCredentails='true'>使用第三方登录</button>
					<image src="../../static/my/head.png" mode=""></image>
				</view>
				<!-- 订单分类 -->
				<view class="order_status">
				 <view class="status" v-for="(item,index) in status" :key="key" @tap="toOrderList(index)">
						<image class="icon" :src="item.url" mode="aspectFill"></image>
						<text>{{item.name}}</text>
					</view>
				</view>
			</view>
		
		<!--  <view class="baiban">
			 
			</view> -->
		</view>
		
 <!-- 
		
		<view class="my_item">
			<view class="img1">
				<image src="../../static/1.jpg" mode="" class="ihh"></image>
			</view>
		</view> -->
		
		
		<view class="center_menu">
		  <view class="menu_item" v-for="(item,index) in menus" :key="index" @tap="toPage(index)">
				<image :src="item.icon" mode="aspectFill"></image>
				<text>{{item.name}}</text>
			</view>
		</view>
		
		 
	</view>
</template>

<script>
	export default {
		data() {
			return {
				avatarUrl:'../../static/我的页面/头像.png',
				nickname:'昵称',
				status: [{
						key: 1,
						name: '未付款',
						url: '../../static/我的页面/未付款.png'
					},
					{
						key: 2,
						name: '已付款',
						url: '../../static/我的页面/已付款.png'
					},
					{
						key: 3,
						name: '已完成',
						url: '../../static/我的页面/已完成.png'
					},
					{
						key: 4,
						name: '收货地址',
						url: '../../static/我的页面/其他渠道.png'
					},
					{
						key: 5,
						name: '晒单中心',
						url: '../../static/我的页面/晒单中心.png'
					}
				],
				menus: [{
				  	
						name: '会员中心',
						icon: '../../static/fumou-center-template/5.png',
						key: 1,
					},
					{
						name: '我的优惠卷',
						icon: '../../static/fumou-center-template/6.png',
						key: 2,
					},
					{
						name: '我的礼品卡',
						icon: '../../static/fumou-center-template/7.png',
						key: 3,
					},
					{
						name: '我的收藏',
						icon: '../../static/fumou-center-template/8.png',
						key: 4,
					},
					{
						name: '垃圾分类',
						icon: '../../static/fumou-center-template/8.png',
						key: 5,
					},
					{
						name: '在线客服',
						icon: '../../static/fumou-center-template/9.png',
						key: 6,
					},
					{
						name: '关于我们',
						icon: '../../static/fumou-center-template/10.png',
						key: 7,
					},
					{
						name: '设置',
						icon: '../../static/fumou-center-template/10.png',
						key: 8,
					}

				]
			};
		},
		methods: {
			clickImg(){
				//跳转到个人中心
				console.log('跳转');
				uni.navigateTo({
					url:'./my_center/index'
				});
			},
		
			toOrderList(index){
				if(index==0){
					uni.navigateTo({
						url:'./order_list/order_list'
					});
				}
				if(index==1){
					uni.navigateTo({
						url:'./order_list/order_list'
					});
				}
				if(index==2){
					uni.navigateTo({
						url:'./order_list/order_list'
					});
				}
				if(index==3){
					uni.navigateTo({
						url:'./order_list/order_list'
					});
				}
				if(index==4){
					uni.navigateTo({
						url:'./my_sunking_center/index'
					});
				}
			},
 
			toPage(index){
				if(index==0){
					uni.navigateTo({
						url:'./my_members/index'
					});
				}
				if(index==1){
					uni.navigateTo({
						url:'./my_coupon/index'
					});
				}
				if(index==2){
					uni.navigateTo({
						url:'./order_list/order_list'
					});
				}
				if(index==3){
					uni.navigateTo({
						url:'./order_list/order_list'
					});
				}
				if(index==4){
					uni.navigateTo({
						url:'./order_list/order_list'
					});
				}
				if(index==5){
					uni.navigateTo({
						url:'./order_list/order_list'
					});
				}
				if(index==6){
					uni.navigateTo({
						url:'./order_list/order_list'
					});
				}
				if(index==7){
					uni.navigateTo({
						url:'./order_list/order_list'
					});
				}
			},
			
			getUserInfo(){
				let that = this;
				uni.login({
				  provider: 'weixin',
				  success: function (loginRes) {
				    console.log(loginRes.authResult);
				    // 获取用户信息
				    uni.getUserInfo({
				      provider: 'weixin',
				      success: function (infoRes) {
								console.log(infoRes);
				        console.log('用户昵称为：' + infoRes.userInfo.nickName);
								that.avatarUrl = infoRes.userInfo.avatarUrl;
								that.nickname = infoRes.userInfo.nickName;
				      }
				    });
				  }
				});
			},
			 

		},
		computed: {

		}
	}
</script>

<style lang="scss">
	
	#buttonInfo{
		font-size: 24upx;
		
	}
	page {
		height: 100%;
	}

	.profily,
	.profily_header {
		border-radius: 8px;
	}

	.center {
		/* height: 100%; */

		/* &_top {
			height: 18%;
			background: url('../../static/fumou-center-template/header.jpg') no-repeat 0% 50%;
			background-size: cover;

			// background: #E6E6E6;
			.mask {
				background: rgba(0, 0, 0, .4);
				height: 100%;
				width: 100%;
			}
		} */

		&_box_bg {
			background: #F9F9F9;
			/* position: relative; */

			.profily {
				/* position: absolute; */
				/* width: 90%; */
				// border:1px solid #F7F7F7;
				margin: 0 auto;
				/* top: -100upx; */
				/* left: 5%; */
				background: #FEFEFE;
				padding: 35upx;
				/* box-sizing: border-box; */
				box-shadow: 0px 2px 5px #EDEDED;
			}
		}
	}

	.base {
		display: flex;
		align-items: center;
		border-bottom: 2px solid #F6F6F6;
		/* padding-bottom: 35upx; */
		/* position: relative; */
		.profily_header {
			height: 120upx;
			width: 120upx;
			background-image: url('../../static/fumou-center-template/header.jpg');
			background-size: 100%;
		}

		text {
			margin-left: 20px;
			font-size: 30upx;
		}
		
		#avatarUrl{
			/* position: relative; */
			height: 120upx;
			width: 120upx;
			border-radius: 8px;
		}
		
		image{
			/* position: absolute; */
			height: 40upx;
			width: 40upx;
			/* right: 0px;
			top:0px; */
		}
	}

	.order_status {
		display: flex;
		justify-content: space-between;
		margin-top: 35upx;

		.status {
			width: 140upx;
			font-size: 24upx;
			text-align: center;
			letter-spacing: .5px;
			display: flex;
			flex-direction: column;
			color: #FFC125;
			.icon {
				width: 50upx;
				height: 50upx;
				margin: 0 auto;
				margin-bottom: 10px;
				
			}
		}
	}

	 

	.center_menu {
		width: 100%;
		/* display: inline-block; */

		.menu_item {
			font-size: 28upx;
			letter-spacing: 1px;
			padding: 14px 5%;
			background: #FEFEFE;
			/* overflow: hidden; */
			box-sizing: border-box;
			display: flex;
			align-items: center;
			/* position: relative; */
			border-bottom: 1px solid #EFEFEF;

			&:hover {
				background: #F6F6F6 !important;
			}

			&::after {
				content: '';
				width: 30upx;
				height: 30upx;
				/* position: absolute; */
				
				background: url('../../static/fumou-center-template/right.png') no-repeat;
				background-size: 100%;
			}

			text:nth-of-type(1) {
				margin-left: 10px;
			}

			image {
				width: 40upx;
				height: 40upx;
			}

			&:nth-of-type(4) {
				margin-top: 10px;
			}
			.my_item{
			width: 100%;
			height: 500upx;
			display: flex;
			justify-content: center;
			margin-right: 800upx;
			margin-top: 20upx;
			margin: 0px auto;
			}
			.img1{
				width: 100%;
				height: 100upx; 
				margin: 0px auto;
				margin-right: 800upx;
			}
			.ihh{
				width: 100%;
				height: 100upx; 
				margin: 0px auto;
				margin-right: 800upx;
		   }
		}
	}
</style>
