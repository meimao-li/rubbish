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
						src:"../../static/find_page/refuse_bin/1.jpg",
						title:'这个碎纸机垃圾桶挺好用的，还挺方便的', 
						//showText:Math.floor(Math.random()+0.5)==1?true:false,
						showText:true,
						text:'您浏览过的足迹',
						showCity:true,
						city:'安徽'
					},
					{
						src:"../../static/find_page/refuse_bin/2.jpg",
						title:'第一次见这样的垃圾桶，颜值是挺高的，放在家里都不舍得扔垃圾了', 
						//showText:Math.floor(Math.random()+0.5)==1?true:false,
						showText:true,
						text:'您浏览过的足迹',
						showCity:true,
						city:'安徽'
					},
					{
						src:"../../static/find_page/refuse_bin/3.jpg",
						title:'放在厨房挺卫生的，好评', 
						//showText:Math.floor(Math.random()+0.5)==1?true:false,
						showText:true,
						text:'您浏览过的足迹',
						showCity:true,
						city:'安徽'
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
						src:"../../static/find_page/refuse_bin/"+Math.floor(Math.random()*3+1)+".jpg",
						title:'春眠不觉晓,处处闻啼鸟.夜来风雨声,花落知多少',
				/* 		orig:Math.floor(Math.random()*1000),
						money:Math.floor(Math.random()*1000), */
						showText:Math.floor(Math.random()+0.5)==1?true:false,
						text:'您浏览过的足迹',
						showCity:Math.floor(Math.random()+0.5)==1?true:false,
						city:'宁波'
					},
					{
						src:"../../static/find_page/refuse_bin/"+Math.floor(Math.random()*3+1)+".jpg",
						title:'寒雨连江夜入吴,平明送客楚山孤.洛阳亲友如相问,一片冰心在玉壶',
						/* orig:Math.floor(Math.random()*1000),
						money:Math.floor(Math.random()*1000), */
						showText:Math.floor(Math.random()+0.5)==1?true:false,
						text:'限时促销小助手为您推荐',
						showCity:Math.floor(Math.random()+0.5)==1?true:false,
						city:'宁波'
					},{
						src:"../../static/find_page/refuse_bin/"+Math.floor(Math.random()*3+1)+".jpg",
						title:'春眠不觉晓,处处闻啼鸟.夜来风雨声,花落知多少',
				/* 		orig:Math.floor(Math.random()*1000),
						money:Math.floor(Math.random()*1000), */
						showText:Math.floor(Math.random()+0.5)==1?true:false,
						text:'您浏览过的足迹',
						showCity:Math.floor(Math.random()+0.5)==1?true:false,
						city:'宁波'
					},
					{
						src:"../../static/find_page/refuse_bin/"+Math.floor(Math.random()*3+1)+".jpg",
						title:'寒雨连江夜入吴,平明送客楚山孤.洛阳亲友如相问,一片冰心在玉壶',
					/* 	orig:Math.floor(Math.random()*1000),
						money:Math.floor(Math.random()*1000), */
						showText:Math.floor(Math.random()+0.5)==1?true:false,
						text:'限时促销小助手为您推荐',
						showCity:Math.floor(Math.random()+0.5)==1?true:false,
						city:'宁波'
					},{
						src:"../../static/find_page/refuse_bin/"+Math.floor(Math.random()*3+1)+".jpg",
						title:'春眠不觉晓,处处闻啼鸟.夜来风雨声,花落知多少',
					/* 	orig:Math.floor(Math.random()*1000),
						money:Math.floor(Math.random()*1000), */
						showText:Math.floor(Math.random()+0.5)==1?true:false,
						text:'您浏览过的足迹',
						showCity:Math.floor(Math.random()+0.5)==1?true:false,
						city:'宁波'
					},
					{
						src:"../../static/find_page/refuse_bin/"+Math.floor(Math.random()*3 +1)+".jpg",
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