<template>
	<view class="container">
		<view class="mu-list">
			<template v-for="item in messageList">
				<view class="mu-list-item" :class="{'mu-list-item-end': item.isSelf}">
					<view :class="{'mu-list-item-left': !item.isSelf, 'mu-list-item-right': item.isSelf}">
						<image v-if="item.image" :src="item.image"></image>
						<view class="message-text">{{item.text}}</view>
					</view>
				</view>
			</template>
		</view>
		
		<view class="bottom-box">
			<input v-model="messageInput" placeholder="发送内容"/>
			<button type="primary" @click="sendMessage">发送</button>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				messageList: [
					{
						isSelf: true,
						text: 'All good! we have some update'
					},
					{
						isSelf: false,
						text: '...'
					},
					{
						isSelf: false,
						text: 'Cool! i hawe somo fcadbacks onthe "How it work section., butoveralt ooks good now!'
					},
					{
						isSelf: true,
						text: 'All good! we have some update',
						image: '../../../static/logo.png'
					}
				],
				messageInput: ''
			}
		},
		methods: {
			sendMessage() {
				if(!this.messageInput) {
					uni.showToast({
						title: '请输入发送内容',
						icon: 'none'
					})
					return
				}
				
				this.messageList.push({
					isSelf: true,
					text: this.messageInput
				})
				
				this.messageInput = ''
			}
		}
	}
</script>

<style>
	.container {
		position: relative;
	}
	
	.mu-list {
		padding: 30rpx;
		box-sizing: border-box;
		margin-bottom: 100rpx;
	}
	
	.mu-list-item {
		display: flex;
		align-items: center;
		justify-content: start;
		margin-bottom: 40rpx;
	}
	
	.mu-list-item-end {
		justify-content: end;
	}
	
	.mu-list-item-left {
		background-color: #FFFFFF;
		border-radius: 20rpx 20rpx 20rpx 0;
		color: #000;
		max-width: 80%;
		padding: 20rpx 30rpx;
		box-sizing: border-box;
	}
	
	.mu-list-item-right {
		background-color: #43D687;
		border-radius: 20rpx 20rpx 0;
		color: #fff;
		max-width: 80%;
		padding: 20rpx 30rpx;
		box-sizing: border-box;
	}
	
	.message-text {
		font-size: 28rpx;
		font-weight: 400;
	}
	
	.mu-list-item image {
		width: 100%;
		height: 200rpx;
		border-radius: 20rpx;
		margin-bottom: 10rpx;
	}
	
	.bottom-box {
		position: fixed;
		left: 0;
		right: 0;
		bottom: 0;
		background-color: #fff;
		padding: 20rpx 30rpx;
		box-sizing: border-box;
		display: flex;
		align-items: center;
	}
	
	.bottom-box input {
		flex: 1;
		background-color: #eee;
		height: 60rpx;
		line-height: 60rpx;
		border-radius: 30rpx;
		padding: 0 40rpx;
		box-sizing: border-box;
		font-size: 28rpx;
		margin-right: 20rpx;
	}
	
	.bottom-box uni-button[type=primary] {
		width: 100rpx;
		height: 50rpx;
		line-height: 50rpx;
		background-color: rgba(67, 214, 135, 1);
		border-radius: 30rpx;
		font-size: 24rpx;
		font-weight: 400;
		color: #FFFFFF;
	}
	
	.bottom-box .button-hover[type=primary] {
		background-color: rgba(67, 214, 135, .6);
	}
	
	.bottom-box uni-button[disabled][type=primary] {
		background-color: rgba(67, 214, 135, .6);
	}
</style>
