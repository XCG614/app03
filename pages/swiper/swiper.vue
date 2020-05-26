<template>
	<view>
		<swiper next-margin="30px" :indicator-dots="true" :autoplay="true" :interval="3000" :duration="1000">
			<swiper-item class="item" v-for="v in swiperData" :key='v'>
				<image :src="v" mode=""></image>
			</swiper-item>
			
		</swiper>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				swiperData:[
					"http://img4.imgtn.bdimg.com/it/u=3812294129,3040612569&fm=26&gp=0.jpg",
					"http://img3.imgtn.bdimg.com/it/u=2065850112,1296058287&fm=26&gp=0.jpg",
					"http://img2.imgtn.bdimg.com/it/u=2183928271,3916848527&fm=26&gp=0.jpg",
					"http://img0.imgtn.bdimg.com/it/u=2216306896,1331241086&fm=26&gp=0.jpg"
					
				]
			}
		},
		methods: {
			
		}
	}
</script>

<style lang="scss">
.item{
	image{
		width: 100%;
	}
	
}
</style>
