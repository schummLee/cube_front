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
			<!-- <input v-model="messageInput" placeholder="发送内容"/>
			<button type="primary" @click="sendMessage">发送</button> -->
			
			<view class="bottom-message" @click="sendMessage('你好吗？')">使用物品</view>
			<view class="bottom-message" @click="sendMessage('很高兴见到你')">攻击BOSS</view>
			<view class="bottom-message" @click="sendMessage('明天见')">离开</view>
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
						text: '你攻击了BOSS'
					},
					{
						isSelf: false,
						text: '你击败了BOSS'
					},
					{
						isSelf: false,
						text: '你获得了新的物品 '
					},
					{
						isSelf: true,
						text: '这是新的物品 请在背包中查看',
						image: '../../../static/logo.png'
					}
				],
				messageInput: ''
			}
		},
		methods: {
			sendMessage(messageText) {
				// if(!this.messageInput) {
				// 	uni.showToast({
				// 		title: '请输入发送内容',
				// 		icon: 'none'
				// 	})
				// 	return
				// }
				
				this.messageList.push({
					isSelf: true,
					text: messageText
				})
				
				uni.request({
					url: '',
					method: 'GET',
					success: (res) => {
						console.log(res)
					}
				})
				
				// this.messageInput = ''
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
		background-color: #373737;
		left: 0;
		right: 0;
		bottom: 0;
		padding: 20rpx 30rpx 140rpx;
		box-sizing: border-box;
		box-shadow: 0rpx 4rpx 10rpx #fff;
		/* display: flex;
		align-items: center; */
	}
	
	.bottom-box .bottom-message {
		background-color: #43D687;
		height: 80rpx;
		line-height: 80rpx;
		padding: 0 30rpx;
		box-sizing: border-box;
		border-radius: 40rpx;
		font-size: 34rpx;
		color: #fff;
		margin-bottom: 20rpx;
		text-align: center;
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