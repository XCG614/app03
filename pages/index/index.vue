<template>
	<view class="content">
		<image class="logo" src="/static/logo.png"></image>
		<view class="text-area">
			<text class="title">{{title}}</text>
		</view>
		<text>{{msg}}</text>
		<navigator url="/pages/newsDetail/newsDetail">跳转新闻详情页</navigator>
		<navigator url="/pages/webview/webview">百度</navigator>
		<button @click="chooseImg">选择图片</button>
		<!-- <image style="width: 100%;" :src="imgUrl" mode=""></image> -->
		<button @click="getLocation">获取地理位置</button>
			
	</view>
</template>

<script>
	import {mapState} from 'vuex';
	export default {
		data() {
			return {
				title: 'Hello',
				imgUrl:''
			}
		},
		computed:{
			...mapState(['msg'])
		},
		onLoad() {

		},
		methods: {
			chooseImg(){
				uni.chooseImage({
					count:1,
					sizeType:["original","compressed"],
					sourceType:["album"],
					success:(e)=>{
						// console.log(e)
						this.imgUrl=e.tempFilePaths[0]
					}
				})
			},
			getLocation(){
				uni.getLocation({
					success: (res) => {
						// console.log(res)
						uni.request({
							url:'https://restapi.amap.com/v3/geocode/regeo',
							data:{
								key:'1e357b4b42a45ed175c3c72ca093c77f',
								location:`${res.longitude},${res.latitude}`
							},
							success:(data)=>{
								console.log(data)
							}
						})
					}
				})
			}
		},
		onNavigationBarSearchInputChanged(e){
			console.log(e.text)  //获取输入框输入的值
		},
		onNavigationBarSearchInputConfirmed(e){
			console.log('用户点击了确认按钮')
		},
		onNavigationBarSearchInputClicked(e){
			console.log('搜索框被点击了')
			//该生命周期需要设置搜索框的disabled:true
		},
		onPullDownRefresh() {   //监听用户下拉刷新的操作
			setTimeout(()=>{
				uni.stopPullDownRefresh()
			},3000)
		},
		onTabItemTap(e) {
			console.log(e)
		},
		
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>
