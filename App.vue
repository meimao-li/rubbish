<script>
	export default {
		globalData:{
			current: 0,
			rubbishList:[],
			totalScore:0,
		},
		//借鉴了Vuex状态管理的思想，组件之间的通信
		//整个应用加载
		onLaunch: function() {
			console.log('App Launch')
		},
		//应用页面出现
		onShow: function() {
			console.log('App Show')
		},
		//应用页面隐藏
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style>
	/*每个页面公共css */
</style>
