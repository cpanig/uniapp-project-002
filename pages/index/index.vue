<template>
	<view class="content">

<!-- 		<scroll-view
		  scroll-x="true"
		  class="scroll-content"
		  :scroll-into-view="scrollIntoindex"
		  :scroll-with-animation="true"
		>
		  <view
			:id="`top${index}`"
		    class="scroll-item"
		    v-for="(item, index) in menus"
		    :key="index"
			@tap="changTap(index)"
		  >
		    <text :class="topBarIndex === index ? 'f-active-color' : 'f-color'">
		      {{item}}
		    </text>
		  </view>
		</scroll-view>
	

	<swiper 
	@change="onChangeTap"
	:current="topBarIndex"
	:circular="true"
	style="width: 100%;"
	>
		<swiper-item  v-for="(item, index) in menus" :key="index">
			<scroll-view scroll-y="true" >
				<view>
					<text>{{item}}</text>
				</view>
			</scroll-view>
		</swiper-item>
	</swiper> -->
	
	
	<swiper
	 class="menus"
	:indicator-dots="true" 
	:interval="3000" 
	:duration="1000">
		<swiper-item class="menus-item">
			<view>
				<gird></gird>
			</view>
		</swiper-item>
		
		<swiper-item class="menus-item">
			<view>
				<gird></gird>
			</view>
		</swiper-item>
	</swiper>
	</view>
</template>

<script>
	import gird from '@/components/common/gird'
	export default {
		data() {
			return {
				// 菜单名称
				menus:[
					"首页",
					"系统管理",
					"综合管理",
					"用户管理",
					"员工管理",
					"人员追踪",
					"查询统计",
					"考勤管理",
					"系统帮助"
				],
				// 菜单的id值，用来切换菜单
				scrollIntoindex: "top0",
				// 菜单的索引
				topBarIndex: 0
			}
		},
		onLoad() {

		},
		methods: {
			changTap(index) {
			  if (this.topBarIndex === index) return false;
			  this.topBarIndex = index;
			  this.scrollIntoindex = `top${index}`;
			},
			// 切换视图
			onChangeTap(e) {
			  this.changTap(e.detail.current);
			}
		},
		components:{
			gird
		}
	}
</script>

<style scoped>
	.content{
		display: flex;
		justify-content: center;
		align-items: center;
	}
	/* 主菜单轮播图 */
	.menus{
		width: 90%;
		height: 750rpx;
		display: flex;
		justify-content: space-around;
		margin-top: 100rpx;
	}
	.menus-item{
		width: 90%;
	}
/* 	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	} */
	.scroll-content {
	  width: 100%;
	  height: 88rpx;
	  white-space: nowrap;
	  position: fixed;
	  bottom: 0;
	}
	.scroll-item {
	  display: inline-block;
	  padding: 10rpx 30rpx;
	  font-size: 36rpx;
	}
	.f-active-color {
	  padding: 10rpx 0;
	  border-bottom: 6rpx solid #49bdfb;
	}
	.f-color{
		color: #636263;
	}
</style>
