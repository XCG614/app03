<template>
	<view>
		<navigator open-type="switchTab" url="../index/index">返回首页</navigator>
		<view v-for="v in 100" :key='v'>新闻详情{{v}}</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			
		},
		onReachBottom(){   //页面拉到底的生命周期函数
			console.log('页面拉到底了')
			//可以用于加载更多数据
		}
	}

</script>

<style>

</style>
