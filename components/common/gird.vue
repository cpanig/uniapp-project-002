<template>
<view>
	<uni-grid :column="3">
	    <uni-grid-item v-for="(item,index) in menus" :key="index">
			<view class="menus-item">
				<view class="iconfont menus-icon" v-html="item.icon"></view>
				<!-- <image :src="item.icon" class="item-img" mode=""></image> -->
				<view class="menus-name">{{ item.name }}</view>
			</view>
	    </uni-grid-item>
	</uni-grid>
</view>
</template>

<script>
	import {uniGrid,uniGridItem } from '@dcloudio/uni-ui'
	export default {
		data() {
			return {
				menus:[
					{name:'盾构防撞',icon:"&#xe607;"},
					{name:'行车视频',icon:"&#xe60e;"},
					{name:'实时定位',icon:"&#xe611;"},
					{name:'信息管理',icon:"&#xe616;"},
					{name:'网络管理',icon:"&#xe65f;"},
					{name:'环境监测',icon:"&#xe626;"},
					{name:'隧道监控',icon:"&#xe685;"},
					{name:'系统设置',icon:"&#xe637;"},
					{name:'更多',icon:"&#xe601;"}
				]
			}
		},
		methods: {
			
		},
		components:{
			uniGrid,
			uniGridItem 
		}
	}
</script>

<style scoped>
.menus-item{
	width: 100%;
	display: flex;
	flex-direction: column;
	align-items: center;
	justify-content: baseline;
	padding: 25% 0;
}
/* 图标 */
.menus-icon{
	color: #FFFFFF;
	font-size: 20rpx;
}
/* 菜单名称 */
.menus-name{
	margin-top: 5rpx;
	color: #FFFFFF;
}

</style>
