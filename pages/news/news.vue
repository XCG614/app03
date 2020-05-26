<template>
	<view>
		<text>这是新闻页</text>
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
		onNavigationBarButtonTap(e) {  //监听头部按钮被点击的生命周期函数
			console.log(e)
			switch(e.index){
				case 0:
				alert('点击了分享按钮');
				break;
				case 1:
				alert('点击了更多按钮');
				break;
				case 2:
				alert('点击了编辑按钮');
				break;
			}
		}
	}
</script>

<style>

</style>
