<template>
	<view>
		<button @click="preview()">预览图片</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				urls:[
					"http://img4.imgtn.bdimg.com/it/u=3812294129,3040612569&fm=26&gp=0.jpg",
					"http://img3.imgtn.bdimg.com/it/u=2065850112,1296058287&fm=26&gp=0.jpg",
					"http://img2.imgtn.bdimg.com/it/u=2183928271,3916848527&fm=26&gp=0.jpg",
					"http://img0.imgtn.bdimg.com/it/u=2216306896,1331241086&fm=26&gp=0.jpg"
				]
			}
		},
		methods: {
			preview(){
				uni.previewImage({
					count:0,
					urls:this.urls
				})
			}
		}
	}
</script>

<style>

</style>
