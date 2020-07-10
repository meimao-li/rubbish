<template>
	<view class="content">
		<zyflow :flowlist="datalist" @flowtap="touchcard" @flowget="adddata" ></zyflow>
	</view>
</template>

<script>
	// 导入瀑布流组件
	import zyflow from "../../../components/zyflow/zyflow.vue"
	export default {
		//注册组件
		components:{
			zyflow
		},
		data() {
			return {
				datalist:[
			 
					{
						src:"../../static/find_page/life/3.jpg",
						title:'喜欢这个颜色', 
						//showText:Math.floor(Math.random()+0.5)==1?true:false,
						showText:true,
						text:'您浏览过的足迹',
						showCity:true,
						city:'广州'
					},
					{
						src:"../../static/find_page/life/4.jpg",
						title:'这种圆圆粉粉的花瓶太可爱了，哈哈哈', 
						//showText:Math.floor(Math.random()+0.5)==1?true:false,
						showText:true,
						text:'您浏览过的足迹',
						showCity:true,
						city:'郑州'
					},
					{
						src:"../../static/find_page/life/5.jpg",
						title:'啊，今年最流行的颜色被我抢到了，而且还是我最喜欢的设计师的设计的，天呐', 
						//showText:Math.floor(Math.random()+0.5)==1?true:false,
						showText:true,
						text:'您浏览过的足迹',
						showCity:true,
						city:'成都'
					},
					{
						src:"../../static/find_page/life/6.jpg",
						title:'这款灯设计的超级贴心，可以变换角度的，而且颜色也很漂亮呦', 
						//showText:Math.floor(Math.random()+0.5)==1?true:false,
						showText:true,
						text:'您浏览过的足迹',
						showCity:true,
						city:'深圳'
					},
					{
						src:"../../static/find_page/life/7.jpg",
						title:'这种花瓶终于被我找到了，既能当摆件，还能装饰，超级喜欢，爱了爱了', 
						//showText:Math.floor(Math.random()+0.5)==1?true:false,
						showText:true,
						text:'您浏览过的足迹',
						showCity:true,
						city:'宁波'
					},
					{
						src:"../../static/find_page/life/8.jpg",
						title:'爱电影，爱生活', 
						//showText:Math.floor(Math.random()+0.5)==1?true:false,
						showText:true,
						text:'您浏览过的足迹',
						showCity:true,
						city:'深圳'
					},
					 
					{
						src:"../../static/find_page/life/9.jpg",
						title:'终于找到了一个能配上我钢笔的笔筒了，太好看了吧这也', 
						//showText:Math.floor(Math.random()+0.5)==1?true:false,
						showText:true,
						text:'您浏览过的足迹',
						showCity:true,
						city:'广州'
					},
				 
					{
						src:"../../static/find_page/life/2.jpg",
						title:'这个小夜灯的灯光不刺眼不错不错', 
						//showText:Math.floor(Math.random()+0.5)==1?true:false,
						showText:true,
						text:'您浏览过的足迹',
						showCity:true,
						city:'安徽'
					},
					{
						src:"../../static/find_page/life/1.jpg",
						title:'我也不知道这个是干嘛用的，只是觉得它好看才买的', 
						//showText:Math.floor(Math.random()+0.5)==1?true:false,
						showText:true,
						text:'您浏览过的足迹',
						showCity:true,
						city:'郑州'
					},
				]
			}
		},
		onLoad() {
			
		},
		methods: {
			touchcard(e){
				/* console.log('点击此项获取到的数据')
				console.log(e);	 */
			},
			adddata(){
				console.log('调用增加数据函数');
				this.datalist = this.datalist.concat([{
						src:"../../static/find_page/life/"+Math.floor(Math.random()*9+1)+".jpg",
						title:'春眠不觉晓,处处闻啼鸟.夜来风雨声,花落知多少',
				/* 		orig:Math.floor(Math.random()*1000),
						money:Math.floor(Math.random()*1000), */
						showText:Math.floor(Math.random()+0.5)==1?true:false,
						text:'您浏览过的足迹',
						showCity:Math.floor(Math.random()+0.5)==1?true:false,
						city:'宁波'
					},
					{
						src:"../../static/find_page/life/"+Math.floor(Math.random()*9+1)+".jpg",
						title:'寒雨连江夜入吴,平明送客楚山孤.洛阳亲友如相问,一片冰心在玉壶',
						/* orig:Math.floor(Math.random()*1000),
						money:Math.floor(Math.random()*1000), */
						showText:Math.floor(Math.random()+0.5)==1?true:false,
						text:'限时促销小助手为您推荐',
						showCity:Math.floor(Math.random()+0.5)==1?true:false,
						city:'宿迁'
					},{
						src:"../../static/find_page/life/"+Math.floor(Math.random()*9+1)+".jpg",
						title:'春眠不觉晓,处处闻啼鸟.夜来风雨声,花落知多少',
				/* 		orig:Math.floor(Math.random()*1000),
						money:Math.floor(Math.random()*1000), */
						showText:Math.floor(Math.random()+0.5)==1?true:false,
						text:'您浏览过的足迹',
						showCity:Math.floor(Math.random()+0.5)==1?true:false,
						city:'南京'
					},
					{
						src:"../../static/find_page/life/"+Math.floor(Math.random()*9+1)+".jpg",
						title:'寒雨连江夜入吴,平明送客楚山孤.洛阳亲友如相问,一片冰心在玉壶',
					/* 	orig:Math.floor(Math.random()*1000),
						money:Math.floor(Math.random()*1000), */
						showText:Math.floor(Math.random()+0.5)==1?true:false,
						text:'限时促销小助手为您推荐',
						showCity:Math.floor(Math.random()+0.5)==1?true:false,
						city:'合肥'
					},{
						src:"../../static/find_page/life/"+Math.floor(Math.random()*9+1)+".jpg",
						title:'春眠不觉晓,处处闻啼鸟.夜来风雨声,花落知多少',
					/* 	orig:Math.floor(Math.random()*1000),
						money:Math.floor(Math.random()*1000), */
						showText:Math.floor(Math.random()+0.5)==1?true:false,
						text:'您浏览过的足迹',
						showCity:Math.floor(Math.random()+0.5)==1?true:false,
						city:'金华'
					},
					{
						src:"../../static/find_page/life/"+Math.floor(Math.random()*9 +1)+".jpg",
						title:'寒雨连江夜入吴,平明送客楚山孤.洛阳亲友如相问,一片冰心在玉壶',
					/* 	orig:Math.floor(Math.random()*1000),
						money:Math.floor(Math.random()*1000), */
						showText:Math.floor(Math.random()+0.5)==1?true:false,
						text:'限时促销小助手为您推荐',
						showCity:Math.floor(Math.random()+0.5)==1?true:false,
						city:'宁波'
					}])
			}
		}
	}
</script>

<style>
	.content {
		width: 100%;
		height: 100%;
		position: absolute;
		background-color: #bfa;
	}
</style>
