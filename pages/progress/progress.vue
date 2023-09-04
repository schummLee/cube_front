<template>
	<view class="container">
		<scroll-view :scroll-x="true">
			<view class="mu-tab">
				<template v-for="(tab, index) in tabList">
					<view class="mu-tab-item" @click="onTabChange(index)">
						<view class="mu-tab-item-text" :class="{'tab-active': index == tabIndex}">{{tab}}</view>
					</view>
				</template>
			</view>
		</scroll-view>
		
		<view class="step-box">
			<uni-steps :options="stepOptions" direction="column" :active="stepIndex" active-color="#222"></uni-steps>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				tabIndex: 0,
				tabList: ['选项1', '选项2', '选项3', '选项4', '选项5'],
				stepIndex: 0,
				stepOptions: [{
					title:'PRESENTATION',
					desc:'presantoton of tho fravel ui Dekits projoct to eEron inaho'
					// 10:00 am-11:25 am
				}, {
					title:'Meetings',
					desc:'13:00-14:00'
				}, {
					title:'Interview',
					desc:'14:00-15:00'
				}, {
					title:'Take a break',
					desc:'15:00-16:00'
				}, {
					title:'Continuo Wire',
					desc:'16:00-17:00'
				}]
			}
		},
		methods: {
			onTabChange(index) {
				this.tabIndex = index
			},
		}
	}
</script>

<style>
	.mu-tab {
		margin-top: 20rpx;
		box-sizing: border-box;
		display: flex;
		align-items: center;
	}
	
	.mu-tab .mu-tab-item {
		width: 200rpx;
		height: 50rpx;
		text-align: center;
		font-size: 32rpx;
		font-weight: 400;
		color: #000;
		padding: 0 20rpx;
		box-sizing: border-box;
	}
	
	.mu-tab-item .mu-tab-item-text {
		background-color: #fff;
		border-radius: 10rpx;
		width: 160rpx;
		height: 50rpx;
		line-height: 50rpx;
	}
	
	.tab-active {
		color: #fff;
		background-color: #43D687 !important;
		border-radius: 10rpx;
	}
	
	.step-box {
		margin: 50rpx 30rpx 30rpx;
		min-height: 400rpx;
		padding: 40rpx 30rpx;
		box-sizing: border-box;
		background-color: #FFFFFF;
		border-radius: 20rpx;
		box-shadow: 2rpx 2rpx 10rpx #D5D5D5;
	}
</style>
