<template>
	<view>
		<view @tap="chooseone(v)" v-for="v in listData" :key='v.title' class="title">
			<text class="left">{{v.title}}</text>
			<!-- <text :class="{right:true,red:v.status==0,blue:v.status==1,orange:v.status==2}">{{v.status==0?'未接单':v.status==1?'已完成':'已接单'}}</text> -->
			<text :class="{right:true,red:v.status==0,blue:v.status==1,orange:v.status==2}">{{getStatus(v)}}</text>
		</view>
	</view>
	
</template>

<script>
	export default {
		data() {
			return {
				listData:[
					{title:'标题1',status:0},
					{title:'标题2',status:1},
					{title:'标题3',status:2}
				]
			}
		},
		methods: {
			chooseone(v){
				alert(v.title)
			},
			getStatus(v){
			// 	switch(v.status){
			// 		case 0:
			// 		return '未接单';
			// 		break;
			// 		case 1:
			// 		return '已完成';
			// 		break;
			// 		case 2:
			// 		return '已接单';
			// 		break;
			// 	}
			if(v.status==0){
				return '未接单'
			}else if(v.status==1){
				return '已完成'
			}else{
				return '已接单'
			}
			},
			
			
		}
	}
</script>

<style lang="scss">
.title{
	display: flex;
	justify-content: space-between;
}
.red{
	color: red;
}
.blue{
	color: blue;
}
.orange{
	color: orange;
}
</style>
