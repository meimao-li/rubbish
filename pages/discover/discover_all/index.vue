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
						src:"../../static/find_page/left1.png",
						title:'选了好久终于选到满意的垃圾桶，家里之前买的不环保，超级喜欢这一款呀',
						showText:true,
						text:'您浏览过的足迹',
						showCity:true,
						city:'广州'
					},
					{
						src:"../../static/find_page/right1.png",
						title:'马卡龙配色的北欧风，又好看又实用，推荐！', 
						showText:true,
						text:'您浏览过的足迹',
						showCity:true,
						city:'郑州'
					},
					{
						src:"../../static/find_page/left2.png",
						title:'各种好评，既有分类小常识，又可以买东西，棒棒哒！', 
						//showText:Math.floor(Math.random()+0.5)==1?true:false,
						showText:true,
						text:'限时促销小助手为您推荐',
						showCity:true,
						city:'北京'
					},
					{
						src:"../../static/find_page/right2.png",
						title:'质感很好，不愧是环保产品，能在立即分类APP里找到心仪的，开心', 
						//showText:Math.floor(Math.random()+0.5)==1?true:false,
						showText:true,
						text:'您浏览过的足迹',
						showCity:true,
						city:'广州'
					},	{
						src:"../../static/find_page/left3.png",
						title:'既好看，又实惠，嘻嘻', 
						//showText:Math.floor(Math.random()+0.5)==1?true:false,
						showText:true,
						text:'限时促销小助手为您推荐',
						showCity:true,
						city:'上海'
					},
					{
						src:"../../static/find_page/right3.png",
						title:'比我在某宝里买的都好啊，这里真的是太好了', 
						//showText:Math.floor(Math.random()+0.5)==1?true:false,
						showText:true,
						text:'您浏览过的足迹',
						showCity:true,
						city:'浙江'
					},
					{
						src:"../../static/find_page/all/1.jpg",
						title:'很喜欢这种款式，很有设计感', 
						//showText:Math.floor(Math.random()+0.5)==1?true:false,
						showText:true,
						text:'您浏览过的足迹',
						showCity:true,
						city:'广州'
					},
					{
						src:"../../static/find_page/all/2.jpg",
						title:'穿上它，我就是整个小区最靓的仔，虽然是围裙吧，但质量也挺好的，还送了一个篮子', 
						//showText:Math.floor(Math.random()+0.5)==1?true:false,
						showText:true,
						text:'您浏览过的足迹',
						showCity:true,
						city:'广州'
					},
					{
						src:"../../static/find_page/all/3.jpg",
						title:'喜欢这个颜色', 
						//showText:Math.floor(Math.random()+0.5)==1?true:false,
						showText:true,
						text:'您浏览过的足迹',
						showCity:true,
						city:'合肥'
					},
					{
						src:"../../static/find_page/all/4.jpg",
						title:'这种圆圆粉粉的花瓶太可爱了，哈哈哈', 
						//showText:Math.floor(Math.random()+0.5)==1?true:false,
						showText:true,
						text:'您浏览过的足迹',
						showCity:true,
						city:'苏州'
					},
					{
						src:"../../static/find_page/all/5.jpg",
						title:'啊，今年最流行的颜色被我抢到了，而且还是我最喜欢的设计师的设计的，天呐', 
						//showText:Math.floor(Math.random()+0.5)==1?true:false,
						showText:true,
						text:'您浏览过的足迹',
						showCity:true,
						city:'广州'
					},
					{
						src:"../../static/find_page/all/6.jpg",
						title:'这款灯设计的超级贴心，可以变换角度的，而且颜色也很漂亮呦', 
						//showText:Math.floor(Math.random()+0.5)==1?true:false,
						showText:true,
						text:'您浏览过的足迹',
						showCity:true,
						city:'宁波'
					},
					{
						src:"../../static/find_page/all/7.jpg",
						title:'这种花瓶终于被我找到了，既能当摆件，还能装饰，超级喜欢，爱了爱了', 
						//showText:Math.floor(Math.random()+0.5)==1?true:false,
						showText:true,
						text:'您浏览过的足迹',
						showCity:true,
						city:'宁波'
					},
					{
						src:"../../static/find_page/all/8.jpg",
						title:'爱电影，爱生活', 
						//showText:Math.floor(Math.random()+0.5)==1?true:false,
						showText:true,
						text:'您浏览过的足迹',
						showCity:true,
						city:'义乌'
					},
					{
						src:"../../static/find_page/all/9.jpg",
						title:'买个小桌子喝下午茶用', 
						//showText:Math.floor(Math.random()+0.5)==1?true:false,
						showText:true,
						text:'您浏览过的足迹',
						showCity:true,
						city:'深圳'
					},
					{
						src:"../../static/find_page/all/10.jpg",
						title:'终于找到了一个能配上我钢笔的笔筒了，太好看了吧这也', 
						//showText:Math.floor(Math.random()+0.5)==1?true:false,
						showText:true,
						text:'您浏览过的足迹',
						showCity:true,
						city:'广州'
					},
					{
						src:"../../static/find_page/all/11.jpg",
						title:'价格真的是超便宜了，而且装纸也特别多，还不错', 
						//showText:Math.floor(Math.random()+0.5)==1?true:false,
						showText:true,
						text:'您浏览过的足迹',
						showCity:true,
						city:'广州'
					},
					{
						src:"../../static/find_page/all/12.jpg",
						title:'这个小夜灯的灯光不刺眼不错不错', 
						//showText:Math.floor(Math.random()+0.5)==1?true:false,
						showText:true,
						text:'您浏览过的足迹',
						showCity:true,
						city:'西安'
					},
					{
						src:"../../static/find_page/all/13.jpg",
						title:'我也不知道这个是干嘛用的，只是觉得它好看才买的', 
						//showText:Math.floor(Math.random()+0.5)==1?true:false,
						showText:true,
						text:'您浏览过的足迹',
						showCity:true,
						city:'广州'
					},
					{
						src:"../../static/find_page/all/14.jpg",
						title:'坐上去还挺舒服的，物流也是超级快', 
						//showText:Math.floor(Math.random()+0.5)==1?true:false,
						showText:true,
						text:'您浏览过的足迹',
						showCity:true,
						city:'广州'
					},
					{
						src:"../../static/find_page/all/15.jpg",
						title:'买的时候不知道是可以折叠的，没想到那么方便，好评', 
						//showText:Math.floor(Math.random()+0.5)==1?true:false,
						showText:true,
						text:'您浏览过的足迹',
						showCity:true,
						city:'浙江'
					},
					{
						src:"../../static/find_page/all/16.jpg",
						title:'夏天就喜欢坐这种编的藤椅，坐上去很是舒服', 
						//showText:Math.floor(Math.random()+0.5)==1?true:false,
						showText:true,
						text:'您浏览过的足迹',
						showCity:true,
						city:'山东'
					},
					{
						src:"../../static/find_page/all/17.jpg",
						title:'这是小朋友的摇摇板凳，我坐上去我就是小朋友了，哈哈哈哈', 
						//showText:Math.floor(Math.random()+0.5)==1?true:false,
						showText:true,
						text:'您浏览过的足迹',
						showCity:true,
						city:'西安'
					},
					{
						src:"../../static/find_page/all/18.jpg",
						title:'我是因为看着它便宜，才买的', 
						//showText:Math.floor(Math.random()+0.5)==1?true:false,
						showText:true,
						text:'您浏览过的足迹',
						showCity:true,
						city:'郑州'
					},
					{
						src:"../../static/find_page/all/19.jpg",
						title:'这可是我们70，80后的回忆啊，没想到还有卖的，我要好好收藏', 
						//showText:Math.floor(Math.random()+0.5)==1?true:false,
						showText:true,
						text:'您浏览过的足迹',
						showCity:true,
						city:'浙江'
					},
					{
						src:"../../static/find_page/all/20.jpg",
						title:'我就只是看图片做的挺有趣才买的，其实也挺不错的', 
						//showText:Math.floor(Math.random()+0.5)==1?true:false,
						showText:true,
						text:'您浏览过的足迹',
						showCity:true,
						city:'北京'
					},
					{
						src:"../../static/find_page/all/21.jpg",
						title:'蘑菇凳好可爱，就特别喜欢这种小凳子，就多买了几个', 
						//showText:Math.floor(Math.random()+0.5)==1?true:false,
						showText:true,
						text:'您浏览过的足迹',
						showCity:true,
						city:'金华'
					},
					{
						src:"../../static/find_page/all/22.jpg",
						title:'抽纸盒也太可爱了吧，朋友来家里都以为是玩具', 
						//showText:Math.floor(Math.random()+0.5)==1?true:false,
						showText:true,
						text:'您浏览过的足迹',
						showCity:true,
						city:'成都'
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
						src:"../../static/find_page/all/"+Math.floor(Math.random()*22+1)+".jpg",
						title:'春眠不觉晓,处处闻啼鸟.夜来风雨声,花落知多少',
				/* 		orig:Math.floor(Math.random()*1000),
						money:Math.floor(Math.random()*1000), */
						showText:Math.floor(Math.random()+0.5)==1?true:false,
						text:'您浏览过的足迹',
						showCity:Math.floor(Math.random()+0.5)==1?true:false,
						city:'北京'
					},
					{
						src:"../../static/find_page/all/"+Math.floor(Math.random()*22+1)+".jpg",
						title:'寒雨连江夜入吴,平明送客楚山孤.洛阳亲友如相问,一片冰心在玉壶',
						/* orig:Math.floor(Math.random()*1000),
						money:Math.floor(Math.random()*1000), */
						showText:Math.floor(Math.random()+0.5)==1?true:false,
						text:'限时促销小助手为您推荐',
						showCity:Math.floor(Math.random()+0.5)==1?true:false,
						city:'成都'
					},{
						src:"../../static/find_page/all/"+Math.floor(Math.random()*22+1)+".jpg",
						title:'春眠不觉晓,处处闻啼鸟.夜来风雨声,花落知多少',
				/* 		orig:Math.floor(Math.random()*1000),
						money:Math.floor(Math.random()*1000), */
						showText:Math.floor(Math.random()+0.5)==1?true:false,
						text:'您浏览过的足迹',
						showCity:Math.floor(Math.random()+0.5)==1?true:false,
						city:'义乌'
					},
					{
						src:"../../static/find_page/all/"+Math.floor(Math.random()*22+1)+".jpg",
						title:'寒雨连江夜入吴,平明送客楚山孤.洛阳亲友如相问,一片冰心在玉壶',
					/* 	orig:Math.floor(Math.random()*1000),
						money:Math.floor(Math.random()*1000), */
						showText:Math.floor(Math.random()+0.5)==1?true:false,
						text:'限时促销小助手为您推荐',
						showCity:Math.floor(Math.random()+0.5)==1?true:false,
						city:'宁波'
					},{
						src:"../../static/find_page/all/"+Math.floor(Math.random()*22+1)+".jpg",
						title:'春眠不觉晓,处处闻啼鸟.夜来风雨声,花落知多少',
					/* 	orig:Math.floor(Math.random()*1000),
						money:Math.floor(Math.random()*1000), */
						showText:Math.floor(Math.random()+0.5)==1?true:false,
						text:'您浏览过的足迹',
						showCity:Math.floor(Math.random()+0.5)==1?true:false,
						city:'广州'
					},
					{
						src:"../../static/find_page/all/"+Math.floor(Math.random()*22+1)+".jpg",
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
