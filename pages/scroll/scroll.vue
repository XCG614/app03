<template>
	<view>
		<scroll-view class="wrap" @scrolltolower="scrolltolower" scroll-y="true" >
			<view :style="{background:randomColor()}" class="item" v-for="v in 100" :key='v'>{{v}}</view>
			<view v-if="show" style="text-align: center;">没有更多数据了</view>
		</scroll-view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				show:false
			}
		},
		methods: {
			randomColor(){
				var random1=Math.floor(Math.random()*225);
				var random2=Math.floor(Math.random()*225);
				var random3=Math.floor(Math.random()*225);
				return `rgb(${random1},${random2},${random3})`
			},
			scrolltolower(){
				console.log('滚动到底了')
				this.show=true;
				setTimeout(()=>{
					this.show=false
				},3000)
			}
		}
	}
</script>

<style lang="scss">
.item{
	height: 50px;
	width: 100%;
}
.wrap{
	height: 100vh;
}
</style>
