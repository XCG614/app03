<template>
	<view>
		<web-view webview-styles="webviewStyle" src="https://www.baidu.com/"></web-view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				webviewStyle:{
					progress:{
						color:'#FF3333'
					}
				}
			}
		},
		methods: {
			
		}
	}
</script>

<style>

</style>
