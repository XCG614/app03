<template>
	<view>
		<!-- #ifdef H5 || APP-PLUS -->
		<text>H5</text>
		<!-- #endif -->
		<view></view>
		<!-- #ifdef MP-WEIXIN -->
		<text>微信小程序</text>
		<!-- #endif -->
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			
		}
	}
</script>

<style>

</style>
