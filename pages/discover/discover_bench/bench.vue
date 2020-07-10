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
						src:"../../static/find_page/bench/9.jpg",
						title:'买个小桌子喝下午茶用', 
						//showText:Math.floor(Math.random()+0.5)==1?true:false,
						showText:true,
						text:'您浏览过的足迹',
						showCity:true,
						city:'威海'
					},
	 
					{
						src:"../../static/find_page/bench/8.jpg",
						title:'坐上去还挺舒服的，物流也是超级快', 
						//showText:Math.floor(Math.random()+0.5)==1?true:false,
						showText:true,
						text:'您浏览过的足迹',
						showCity:true,
						city:'宿迁'
					},
					{
						src:"../../static/find_page/bench/7.jpg",
						title:'买的时候不知道是可以折叠的，没想到那么方便，好评', 
						//showText:Math.floor(Math.random()+0.5)==1?true:false,
						showText:true,
						text:'您浏览过的足迹',
						showCity:true,
						city:'成都'
					},
					{
						src:"../../static/find_page/bench/6.jpg",
						title:'夏天就喜欢坐这种编的藤椅，坐上去很是舒服', 
						//showText:Math.floor(Math.random()+0.5)==1?true:false,
						showText:true,
						text:'您浏览过的足迹',
						showCity:true,
						city:'宁波'
					},
					{
						src:"../../static/find_page/bench/5.jpg",
						title:'这是小朋友的摇摇板凳，我坐上去我就是小朋友了，哈哈哈哈', 
						//showText:Math.floor(Math.random()+0.5)==1?true:false,
						showText:true,
						text:'您浏览过的足迹',
						showCity:true,
						city:'上海'
					},
					{
						src:"../../static/find_page/bench/4.jpg",
						title:'我是因为看着它便宜，才买的', 
						//showText:Math.floor(Math.random()+0.5)==1?true:false,
						showText:true,
						text:'您浏览过的足迹',
						showCity:true,
						city:'深圳'
					},
					{
						src:"../../static/find_page/bench/2.jpg",
						title:'这可是我们70，80后的回忆啊，没想到还有卖的，我要好好收藏', 
						//showText:Math.floor(Math.random()+0.5)==1?true:false,
						showText:true,
						text:'您浏览过的足迹',
						showCity:true,
						city:'郑州'
					},
					{
						src:"../../static/find_page/bench/3.jpg",
						title:'我就只是看图片做的挺有趣才买的，其实也挺不错的', 
						//showText:Math.floor(Math.random()+0.5)==1?true:false,
						showText:true,
						text:'您浏览过的足迹',
						showCity:true,
						city:'金华'
					},
					{
						src:"../../static/find_page/bench/1.jpg",
						title:'蘑菇凳好可爱，就特别喜欢这种小凳子，就多买了几个', 
						//showText:Math.floor(Math.random()+0.5)==1?true:false,
						showText:true,
						text:'您浏览过的足迹',
						showCity:true,
						city:'广州'
					},
					 
					
					/* {
						src:"../../static/"+Math.floor(Math.random()*4+1)+".jpg",
						title:'春眠不觉晓,处处闻啼鸟.夜来风雨声,花落知多少', 
						showText:Math.floor(Math.random()+0.5)==1?true:false,
						text:'限时促销小助手为您推荐'
					},
					{
						src:"../../static/"+Math.floor(Math.random()*4+1)+".jpg",
						title:'寒雨连江夜入吴,平明送客楚山孤.洛阳亲友如相问,一片冰心在玉壶', 
						showText:Math.floor(Math.random()+0.5)==1?true:false,
						text:'限时促销小助手为您推荐'
					} */
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
						src:"../../static/find_page/bench/"+Math.floor(Math.random()*9+1)+".jpg",
						title:'春眠不觉晓,处处闻啼鸟.夜来风雨声,花落知多少',
				/* 		orig:Math.floor(Math.random()*1000),
						money:Math.floor(Math.random()*1000), */
						showText:Math.floor(Math.random()+0.5)==1?true:false,
						text:'您浏览过的足迹',
						showCity:Math.floor(Math.random()+0.5)==1?true:false,
						city:'山东'
					},
					{
						src:"../../static/find_page/bench/"+Math.floor(Math.random()*9+1)+".jpg",
						title:'寒雨连江夜入吴,平明送客楚山孤.洛阳亲友如相问,一片冰心在玉壶',
						/* orig:Math.floor(Math.random()*1000),
						money:Math.floor(Math.random()*1000), */
						showText:Math.floor(Math.random()+0.5)==1?true:false,
						text:'限时促销小助手为您推荐',
						showCity:Math.floor(Math.random()+0.5)==1?true:false,
						city:'深圳'
					},{
						src:"../../static/find_page/bench/"+Math.floor(Math.random()*9+1)+".jpg",
						title:'春眠不觉晓,处处闻啼鸟.夜来风雨声,花落知多少',
				/* 		orig:Math.floor(Math.random()*1000),
						money:Math.floor(Math.random()*1000), */
						showText:Math.floor(Math.random()+0.5)==1?true:false,
						text:'您浏览过的足迹',
						showCity:Math.floor(Math.random()+0.5)==1?true:false,
						city:'宁波'
					},
					{
						src:"../../static/find_page/bench/"+Math.floor(Math.random()*9+1)+".jpg",
						title:'寒雨连江夜入吴,平明送客楚山孤.洛阳亲友如相问,一片冰心在玉壶',
					/* 	orig:Math.floor(Math.random()*1000),
						money:Math.floor(Math.random()*1000), */
						showText:Math.floor(Math.random()+0.5)==1?true:false,
						text:'限时促销小助手为您推荐',
						showCity:Math.floor(Math.random()+0.5)==1?true:false,
						city:'北京'
					},{
						src:"../../static/find_page/bench/"+Math.floor(Math.random()*9+1)+".jpg",
						title:'春眠不觉晓,处处闻啼鸟.夜来风雨声,花落知多少',
					/* 	orig:Math.floor(Math.random()*1000),
						money:Math.floor(Math.random()*1000), */
						showText:Math.floor(Math.random()+0.5)==1?true:false,
						text:'您浏览过的足迹',
						showCity:Math.floor(Math.random()+0.5)==1?true:false,
						city:'义乌'
					},
					{
						src:"../../static/find_page/bench/"+Math.floor(Math.random()*9+1)+".jpg",
						title:'寒雨连江夜入吴,平明送客楚山孤.洛阳亲友如相问,一片冰心在玉壶',
					/* 	orig:Math.floor(Math.random()*1000),
						money:Math.floor(Math.random()*1000), */
						showText:Math.floor(Math.random()+0.5)==1?true:false,
						text:'限时促销小助手为您推荐',
						showCity:Math.floor(Math.random()+0.5)==1?true:false,
						city:'浙江'
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
