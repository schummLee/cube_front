<template>
	<view class="container">
		<view class="top-container">
			<view class="user-container">
				<image src="../../../static/logo.png"></image>
				<view class="user-info">
					<view class="user-name">用户名</view>
					<progress :percent="100" :stroke-width="6"/>
				</view>
			</view>
		</view>
		
		<view class="mu-box">
			<view class="mu-box-label">背包</view>
			<view class="mu-grid">
				<template v-for="(item, index) in goods">
					<view class="mu-grid-item">
						<image src="../../../static/logo.png"></image>
					</view>
				</template>
			</view>
		</view>
		
		<view class="mu-box">
			<view class="mu-box-label">仓库</view>
			<view class="mu-grid">
				<template v-for="(item, index) in goods">
					<view class="mu-grid-item">
						<image src="../../../static/logo.png"></image>
					</view>
				</template>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				goods: [
					{}, {}, {}, {}, {}, {}, {}, {}, 
					{}, {}, {}, {}, {}, {}, {}, {}, 
					{}, {}, {}, {}, {}, {}, {}, {}, 
					{}, {}, {}, {}, {}, {}, {}, {}, 
					{}, {}, {}, {}, {}, {}, {}, {},
				]
			}
		},
		methods: {
			
		}
	}
</script>

<style>
	.top-container {
		padding: 40rpx 30rpx;
		box-sizing: border-box;
		display: flex;
		flex-direction: column-reverse;
	}
	
	.user-container {
		display: flex;
		align-items: center;
	}
	
	.user-container image {
		width: 100rpx;
		height: 100rpx;
		border-radius: 50%;
	}
	
	.user-container .user-info {
		flex: 1;
		margin: 0 30rpx;
		color: #fff;
		font-size: 32rpx;
	}
	
	.user-name {
		margin-bottom: 20rpx;
	}
	
	.container>>>.uni-progress {
		width: 80%;
	}
	
	.container>>>.uni-progress-bar {
		border-radius: 3px;
	}
	
	.container>>>.uni-progress-inner-bar {
		border-radius: 3px;
	}
	
	.mu-box {
		margin: 40rpx 30rpx 0;
	}
	
	.mu-box .mu-box-label {
		color: #fff;
		padding: 0 20rpx;
	}
	
	.mu-box .mu-grid {
		margin-top: 10rpx;
		background-color: #222;
		padding: 20rpx;
		box-sizing: border-box;
		border-radius: 10rpx;
		display: grid;
		grid-template-columns: 1fr 1fr 1fr 1fr 1fr 1fr 1fr 1fr;
		grid-column-gap: 15rpx;
		grid-row-gap: 15rpx;
	}
	
	.mu-grid .mu-grid-item {
		height: 70rpx;
		background-color: #fff;
		padding: 2rpx;
		box-sizing: border-box;
	}
	
	.mu-grid-item image {
		width: 100%;
		height: 100%;
	}
</style>
