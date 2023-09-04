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
					<view class="title">4.8</view>
					<view class="desc">描述描述描述描述描述</view>
				</view>
			</view>
			<view class="mu-list-item" @click="openDetatil">
				<image src="../../../static/logo.png"></image>
				<view class="mu-list-item-content">
					<view class="title">4.8</view>
					<view class="desc">描述描述描述描述描述</view>
				</view>
			</view>
			<view class="mu-list-item" @click="openDetatil">
				<image src="../../../static/logo.png"></image>
				<view class="mu-list-item-content">
					<view class="title">4.8</view>
					<view class="desc">描述描述描述描述描述</view>
				</view>
			</view>
		</view>
		
		<view class="step-box">
			<view class="step-label">Ongoing Order</view>
			<view class="step-card" @click="openProgress">
				<view class="step-card-title">Pickup in 32mins</view>
				<view class="mu-step">
					<view class="mu-step-item mu-step-item-active">
						<image src="../../../static/logo.png"></image>
					</view>
					<view class="mu-step-line"></view>
					<view class="mu-step-item">
						<image src="../../../static/logo.png"></image>
					</view>
					<view class="mu-step-line"></view>
					<view class="mu-step-item">
						<image src="../../../static/logo.png"></image>
					</view>
				</view>
				
				<view class="step-card-content">
					这里是阶段内容
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			openMessage() {
				uni.navigateTo({
					url: '/pages/chat/message/message'
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
		background-color: #FFFFFF;
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
		color: #000;
		font-size: 32rpx;
		font-weight: bold;
	}
	
	.mu-list-item-content .desc {
		color: #999;
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
		background-color: #FFFFFF;
		border-radius: 20rpx;
		margin-bottom: 30rpx;
		box-shadow: 2rpx 2rpx 10rpx #D5D5D5;
	}
	
	.step-card .step-card-title {
		color: #000;
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
		background-color: #43D687;
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
		background-color: #43D687;
	}
	
	.step-card-content {
		margin-top: 30rpx;
		color: #999;
		font-size: 28rpx;
	}
</style>
