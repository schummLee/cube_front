<template>
	<view class="container">
		<view class="game-list">
			<template v-for="item in gameList">
				<view class="game-list-item" @click="openGame">
					<image :src="item.banner"></image>
				</view>
			</template>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				gameList: [{
					banner: '../../../static/images/banner.png'
				}, {
					banner: '../../../static/images/banner.png'
				}, {
					banner: '../../../static/images/banner.png'
				}]
			}
		},
		onLoad() {
			this.getGameList();
		},
		methods: {
			getGameList() {
				uni.request({
					url: '',
					method: 'GET',
					success: (res) => {
						console.log(res)
					}
				})
			},
			openGame() {
				uni.navigateTo({
					url: '/pages/games/index/index'
				})
			}
		}
	}
</script>

<style>
	.game-list {
		padding: 40rpx 30rpx;
		box-sizing: border-box;
	}
	
	.game-list-item {
		margin-bottom: 30rpx;
	}
	
	.game-list-item image {
		width: 100%;
		height: 300rpx;
		border-radius: 20rpx;
	}
</style>
