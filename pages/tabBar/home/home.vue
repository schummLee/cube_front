<template>
	<view class="container">
		<view class="status_bar">
			<view class="nav-container">
				<view class="title">HOME</view>
				<uni-icons type="chat-filled" color="#FFFFFF" size="26" @click="openMessage"></uni-icons>
			</view>
		</view>
		
		<view class="mu-list">
			<view class="mu-list-item" @click="openDetatil">
				<image src="../../../static/logo.png"></image>
				<view class="mu-list-item-content">
					<view class="title">最后一次魔方扫描记录</view>
					<view class="desc">16：00：32</view>
				</view>
			</view>
			<view class="mu-list-item" @click="openDetatil">
				<image src="../../../static/logo.png"></image>
				<view class="mu-list-item-content">
					<view class="title">魔方扫描记录</view>
					<view class="desc">魔方扫描记录</view>
				</view>
			</view>
			<view class="mu-list-item" @click="openDetatil">
				<image src="../../../static/logo.png"></image>
				<view class="mu-list-item-content">
					<view class="title">魔方扫描记录</view>
					<view class="desc">魔方扫描记录</view>
				</view>
			</view>
		</view>
		
		<view class="step-box">
			<view class="step-label">任务进行中</view>
			<view class="step-card" @click="openProgress">
				<view class="step-card-title">阶段一</view>
				<view class="mu-step">
					<template v-for="(item, index) in stepList">
						<view v-if="index > 0" class="mu-step-line" :class="{'mu-step-line-active': stepIndex >= index}"></view>
						<view class="mu-step-item" :class="{'mu-step-item-active': stepIndex >= index}">
							<image src="../../../static/logo.png"></image>
						</view>
					</template>
				</view>
				
				<view class="step-card-content">
					<view class="step-title">{{stepOptions[stepIndex].title}}</view>
					<view class="step-desc">{{stepOptions[stepIndex].desc}}</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				stepIndex: 0,
				stepList: [{}, {}, {}, {}, {}],
				stepOptions: [{
					title:'击败攻击小镇的敌人',
					desc:' 任务奖励： 50 金币'
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
		onShow() {
			this.stepIndex = uni.getStorageSync("stepIndex") || 0
			
			uni.request({
				url: '',
				method: 'GET',
				success: (res) => {
					console.log(res)
				}
			})
		},
		methods: {
			openMessage() {
				uni.navigateTo({
					url: '/pages/mine/message/message'
				})
			},
			openDetatil() {
				uni.navigateTo({
					url: '/pages/games/index/index'
				})
			},
			openProgress() {
				uni.navigateTo({
					url: '/pages/progress/progress'
				})
			}
		}
	}
</script>

<style>
	.container {
		
	}
	
	.status_bar {
		padding: calc(var(--status-bar-height) + 20rpx) 0 0;
	}
	
	.nav-container {
		display: flex;
		align-items: center;
		justify-content: space-between;
		padding: 30rpx;
		box-sizing: border-box;
	}
	
	.nav-container .title {
		color: #fff;
		font-size: 40rpx;
		font-weight: bold;
	}
	
	.nav-container image {
		width: 44rpx;
		height: 44rpx;
		margin-left: 42rpx;
	}
	
	.mu-list {
		padding: calc(var(--status-bar-height) + 150rpx) 30rpx 20rpx;
		box-sizing: border-box;
	}
	
	.mu-list-item {
		min-height: 160rpx;
		padding: 40rpx 30rpx;
		box-sizing: border-box;
		background-color: #43D687;
		border-radius: 20rpx;
		margin-bottom: 30rpx;
		box-shadow: 2rpx 2rpx 10rpx #D5D5D5;
		display: flex;
		align-items: center;
	}
	
	.mu-list-item image {
		width: 80rpx;
		height: 80rpx;
		border-radius: 50%;
		margin-right: 30rpx;
	}
	
	.mu-list-item .mu-list-item-content {
		flex: 1;
	}
	
	.mu-list-item-content .title {
		color: #fff;
		font-size: 32rpx;
		font-weight: bold;
	}
	
	.mu-list-item-content .desc {
		color: #fff;
		font-size: 24rpx;
		font-weight: 400;
		margin-top: 10rpx;
	}
	
	.step-box {
		margin: 20rpx 30rpx 0;
	}
	
	.step-box .step-label {
		color: #fff;
		font-size: 32rpx;
		font-weight: bold;
	}
	
	.step-box .step-card {
		margin-top: 20rpx;
		min-height: 400rpx;
		padding: 40rpx 60rpx;
		box-sizing: border-box;
		background-color: #43D687;
		border-radius: 20rpx;
		margin-bottom: 30rpx;
		box-shadow: 2rpx 2rpx 10rpx #D5D5D5;
	}
	
	.step-card .step-card-title {
		color: #fff;
		font-size: 28rpx;
		font-weight: bold;
	}
	
	.step-card .mu-step {
		margin-top: 20rpx;
		display: flex;
		align-items: center;
	}
	
	.mu-step .mu-step-item {
		width: 60rpx;
		height: 60rpx;
		border-radius: 50%;
		background-color: #eee;
		padding: 10rpx;
		box-sizing: border-box;
		z-index: 100;
	}
	
	.mu-step .mu-step-item-active {
		background-color: #2B9939;
	}
	
	.mu-step image {
		width: 40rpx;
		height: 40rpx;
		border-radius: 50%;
	}
	
	.mu-step .mu-step-line {
		flex: 1;
		height: 30rpx;
		background-color: #eee;
		margin-left: -10rpx;
		margin-right: -10rpx;
	}
	
	.mu-step-line-active {
		background-color: #2B9939 !important;
	}
	
	.step-card-content {
		margin-top: 30rpx;
		color: #fff;
		font-size: 28rpx;
	}
	
	.step-title {
		font-size: 32rpx;
		font-weight: bold;
	}
	
	.step-desc {
		margin-top: 20rpx;
	}
</style>
