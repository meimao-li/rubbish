<template>
	<view class="center">
		
		<view class="center_box_bg">
			<view class="profily">
				<view class="base">
					<image :src="avatarUrl" mode="" id="avatarUrl" ></image>
					<text class="my">张先生</text>
					<view class="location">
						<!-- 定位 -->
						<view class="map">
							<text class="zone">Z1</text>
							<view class="text_name1">
								<text class="name2">高级分类生活家</text>
							</view>
						</view>
				</view>
			</view>
		</view>
		</view>
		
		
		<view class="center_menu">
		  <view class="menu_item" v-for="(item,index) in menus" :key="index" @tap="toPage(index)">
				<image :src="item.icon" mode="aspectFill"></image>
				<view >
					<text class="item_name">{{item.name}}</text>
					<view class="text_name">
						<text class="name1">{{item.name1}}</text>
					</view>
				</view>
			</view>
		</view>
		
		 
	</view>
</template>

<script>
	export default {
		data() {
			return {
				avatarUrl:'../../../static/my/head.png',
				nickname:'昵称',
 
				menus: [{
				  	
						name: '￥370升级礼',
						name1: '多档优惠低至8.9折',
						icon: '../../../static/my_vip/icon1.png',
						key: 1,
					},
					{
						name: '生日礼',
						name1: '优惠卷全场可用',
						icon: '../../../static/my_vip/icon2.png',
						key: 2,
					},
					{
						name: '专属会员价',
						name1: '精选商品专属优惠',
						icon: '../../../static/my_vip/icon3.png',
						key: 3,
					},
					{
						name: '9%晒单奖励',
						name1: '晒单奖励多多',
						icon: '../../../static/my_vip/icon4.png',
						key: 4,
					},
					{
						name: '会员惊喜',
						name1: '不定期会员活动，给你惊喜',
						icon: '../../../static/my_vip/icon5.png',
						key: 5,
					},
					{
						name: '线下活动',
						name1: '升级至Z4，开启线下活动邀请',
						icon: '../../../static/my_vip/icon6.png',
						key: 6,
					} 
				]
			};
		},
		methods: {
		},
		computed: {
		}
	}
</script>

<style lang="scss">
	.item_name{
		font-size: 36upx;
	}
	.my{
		font-size: 18upx;
		color: #999999;
	}
	.zone{
		justify-content: flex-end; 
		font-size: 67upx;
		font-weight: bold;
	}
 
	.location{
		display: flex;
		justify-content: flex-end; 
		margin-left: 160upx;
		 
	}
 
	/* 搜索 */
	.search{
		display: flex;
		justify-content: flex-end;/* 右对齐 */
		 
	}
	
	.name1{
		font-size: 20upx;
		color: #999999;
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
		margin-top: 30upx;
		/* padding-bottom: 35upx; */
		/* position: relative; */
		.profily_header {
			height: 120upx;
			width: 120upx;
			background-image: url('../../../static/fumou-center-template/header.jpg');
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
			font-size: 30upx;
			letter-spacing: 1px;
			padding: 14px 5%;
			background: #FEFEFE;
			/* overflow: hidden; */
			height: 140upx;
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
				
				background: url('../../../static/fumou-center-template/right.png') no-repeat;
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
	
	.text_name{
		height: 27upx;
		display: flex;
		 
		 
	}
	.name1{
		justify-content: flex-start;
		margin-left: 200upx;
	}
</style>
