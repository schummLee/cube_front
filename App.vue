<script>
	export default {
		onLaunch: function() {
			console.log('App Launch')
			
			// 设置中间凸起按钮点击事件
			uni.onTabBarMidButtonTap(() => {
				// #ifdef APP-PLUS
				uni.scanCode({
					scanType: ['qrCode'],
					success: (res) => {
						console.log(res)
						let result = encodeURIComponent(res.result);
						uni.navigateTo({
							url: `/pages/index/index?result=${result}`
						})
					}
				})
				// #endif
			})
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style>
	/*每个页面公共css */
	/*每个页面公共css */
	page {
		height: 100%;
		background-color: #373737;
	}
	
	.container {
		width: 100%;
		height: 100%;
		overflow-y: auto;
	}
	
	.status_bar {
		padding: var(--status-bar-height) 0 0;
		box-sizing: border-box;
		width: 100%;
		background-color: transparent;
		position: fixed;
		z-index: 998;
	}
	
	::-webkit-scrollbar {
		display: none;
		width: 0 !important;
		height: 0 !important;
		-webkit-appearance: none;
		background: transparent;
	}
</style>
