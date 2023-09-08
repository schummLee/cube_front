<template>
	<view class="container">
		<view class="user-container">
			<image src="../../../static/logo.png"></image>
			<view style="margin-left: 30rpx;">
				<view class="user-name">用户名</view>
				<uni-rate v-model="rateValue" icon-type="heart-filled" activeColor="#FF0000" disabledColor="#FF0000" disabled></uni-rate>
				<uni-rate v-model="rateValue" activeColor="#ffca3e" disabledColor="#ffca3e" disabled></uni-rate>
			</view>
		</view>
		
		<view class="attribute-box">
			<view class="attribute-item">
				<image src="../../../static/logo.png"></image>
				<view class="attribute-title">攻击力</view>
				<view class="attribute-value">100</view>
			</view>
			<view class="attribute-item">
				<image src="../../../static/logo.png"></image>
				<view class="attribute-title">防御力</view>
				<view class="attribute-value">80</view>
			</view>
			<view class="attribute-item">
				<image src="../../../static/logo.png"></image>
				<view class="attribute-title">生命力</view>
				<view class="attribute-value">9600</view>
			</view>
		</view>
		
		<view class="mu-box">
			<view class="mu-box-label">背包</view>
			<view class="mu-grid">
				<template v-for="(item, index) in goods">
					<view class="mu-grid-item" @click="showGoods">
						<image v-if="item.image" :src="item.image"></image>
					</view>
				</template>
			</view>
		</view>
		
		<view class="mu-box">
			<view class="mu-box-label">仓库</view>
			<view class="mu-grid">
				<template v-for="(item, index) in goods">
					<view class="mu-grid-item" @click="showGoods">
						<image v-if="item.image" :src="item.image"></image>
					</view>
				</template>
			</view>
		</view>
		
		<uni-popup ref="goodsPopup" type="center">
			<view class="goods-box">
				<view class="goods-title">
					<image src="../../../static/logo.png"></image>
					<view>复活符</view>
				</view>
				<view class="goods-detail">
					<view>售价：1000</view>
					<view class="goods-desc">使用后立即复活，使用后立即复活，使用后立即复活，使用后立即复活，使用后立即复活，使用后立即复活，使用后立即复活</view>
				</view>
			</view>
		</uni-popup>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				rateValue: 4,
				goods: [
					{image: '../../../static/logo.png'}, 
					{image: '../../../static/logo.png'},
					{image: '../../../static/logo.png'}, 
					{image: '../../../static/logo.png'}, 
					{image: '../../../static/logo.png'}, 
					{image: '../../../static/logo.png'}, 
					{image: '../../../static/logo.png'}, 
					{image: '../../../static/logo.png'}, 
					{image: '../../../static/logo.png'}, 
					{image: '../../../static/logo.png'}, 
					{}, {}, {}, {}, {}, {}, {}, {}, 
					{}, {}, {}, {}, {}, {}, {}, {}, 
					{}, {}, {}, {}, {}, {}, {}, {}, 
					{}, {}, {}, {}, {}, {},
				]
			}
		},
		onLoad() {
			this.getUserInfo()
		},
		methods: {
			getUserInfo() {
				uni.request({
					url: '',
					method: 'GET',
					success: (res) => {
						console.log(res)
					}
				})
			},
			showGoods() {
				this.$refs.goodsPopup.open()
			}
		}
	}
</script>

<style>
	.user-container {
		padding: 40rpx 30rpx;
		box-sizing: border-box;
		display: flex;
		/* flex-direction: column; */
		align-items: center;
		justify-content: center;
	}
	
	.user-container image {
		width: 150rpx;
		height: 150rpx;
		border-radius: 10rpx;
	}
	
	.user-container .user-name {
		color: #fff;
		font-size: 32rpx;
	}
	
	.container>>>.uni-progress {
		width: 60%;
	}
	
	.container>>>.uni-progress-bar {
		border-radius: 3px;
	}
	
	.container>>>.uni-progress-inner-bar {
		border-radius: 3px;
	}
	
	.user-container>>>.uni-rate {
		margin-top: 10rpx;
	}
	
	.attribute-box {
		margin-top: 30rpx;
	}
	
	.attribute-item {
		display: flex;
		align-items: center;
		justify-content: center;
		margin-bottom: 20rpx;
	}
	
	.attribute-item image {
		width: 30rpx;
		height: 30rpx;
		margin-right: 10rpx;
	}
	
	.attribute-item .attribute-title {
		width: 120rpx;
		color: #fff;
		font-size: 30rpx;
	}
	
	.attribute-item .attribute-value {
		width: 100rpx;
		color: #fff;
		font-size: 28rpx;
	}
	
	.mu-box {
		margin: 40rpx 30rpx 40rpx;
	}
	
	.mu-box .mu-box-label {
		background-color: #43D687;
		color: #fff;
		padding: 10rpx 30rpx;
		border-radius: 10rpx;
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
		background-color: #373737;
		padding: 2rpx;
		box-sizing: border-box;
		border-radius: 10rpx;
	}
	
	.mu-grid-item image {
		width: 100%;
		height: 100%;
	}
	
	.goods-box {
		width: 500rpx;
		background-color: #fff;
		border-radius: 20rpx;
		padding: 30rpx;
		box-sizing: border-box;
	}
	
	.goods-title {
		display: flex;
		align-items: center;
		font-size: 32rpx;
		color: #000;
		font-weight: bold;
	}
	
	.goods-title image {
		width: 40rpx;
		height: 40rpx;
		margin-right: 20rpx;
	}
	
	.goods-detail {
		font-size: 28rpx;
		color: #333;
		font-weight: 400;
		margin-top: 20rpx;
	}
	
	.goods-detail .goods-desc {
		color: #666;
		margin-top: 10rpx;
		line-height: 1.5;
	}
</style>
