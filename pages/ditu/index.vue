<template>
    <view>
        <map style="width:100%;height:85vh;":latitude="latitude":longitude="longitude" ></map>
    </view>
</template>

<script>
	export default {
	    data() {
	        return {
				// 经纪人id
				      　　 agentId:0,
				       　　title: 'map', //地图标题
				       　　latitude: 40.013305,  //纬度
				      　　 longitude: 118.685713,  //经度
				　　　　　　
	   }  
	},
	methods:{}
	
	}
	
</script>

<style>
</style>
