<template>
	<view class="all">
		<view>
			<image src="../../static/ball.gif" style="width: 100%;z-index: -1;"></image>
			<view style="position: relative;top: -20rpx;width: 100%;height: 20rpx;background: linear-gradient(#999999, #336666);z-index: -1;opacity: 0.3;"></view>
		</view>
		
		<view class="bottom_page">
			<view class="top_rect">
				<text style="font-size: 45rpx;font-weight: bold;align-self: center;width: 100%;">不会写捐款</text>
				<br>
				<text style="font-size: 25rpx;font-weight: bold;width: 70%;color: #888888;">填写信息，立即开始筹款，构建区块链存证记录</text>
				<button class="top_button" @click="go_for_help">立&nbsp即&nbsp筹&nbsp款</button>
			</view>
			<view class="mid_rect">
				<view style="display: flex;flex-direction: row;align-items: center;">
					<view style="font-size: 25rpx;color: #8F8F94;height: auto;" @click="go_acticle">在线咨询</view>
					<image src="https://img-blog.csdnimg.cn/20210329020627260.png#pic_center"
						style="width: 40rpx;height: 40rpx;"></image>
				</view>
				<view style="display: flex;flex-direction: row;align-items: center;" @click="go_pho">
					<view style="font-size: 25rpx;color: #8F8F94;height: auto;">电话咨询</view>
					<image src="https://img-blog.csdnimg.cn/20210329020627298.png#pic_center"
						style="width: 40rpx;height: 40rpx;"></image>
				</view>
			</view>
			<swiper class="swiper" :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval"
				:duration="duration">
				<swiper-item @click="go_acticle">
					<view class="swiper-item uni-bg-red">
						<image src="../../static/chain.jpg" class="big"></image>
						<view class="bottom_item">
							<view class="card">
								<image src="../../static/chain.jpg" class="small"></image>
								<text class="small_text">小丑里的疯子发起 2020 0312</text>
							</view>
							<view class="low">
								<view class="text_low">
									<text style="color: #007c00;">500.0</text>
									<text>金额</text>
								</view>
								<view class="text_low">
									<text>500.0</text>
									<text>金额</text>
								</view>
								<view class="text_low">
									<text>500.0</text>
									<text>金额</text>
								</view>

							</view>
						</view>
					</view>
				</swiper-item>
				<swiper-item>
					<view class="swiper-item uni-bg-red">
						<image
							src="https://img-blog.csdnimg.cn/20210329021241215.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1dlY2hhdF9WaW5jZXJv,size_16,color_FFFFFF,t_70#pic_center"
							class="big"></image>
						<view class="bottom_item">
							<view class="card">
								<image
									src="https://img-blog.csdnimg.cn/20210329021241215.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1dlY2hhdF9WaW5jZXJv,size_16,color_FFFFFF,t_70#pic_center"
									class="small"></image>
								<text class="small_text">小丑里的疯子发起 2020 0312</text>
							</view>
							<view class="low">
								<view class="text_low">
									<text style="color: #007c00;">500.0</text>
									<text>金额</text>
								</view>
								<view class="text_low">
									<text>500.0</text>
									<text>金额</text>
								</view>
								<view class="text_low">
									<text>500.0</text>
									<text>金额</text>
								</view>

							</view>
						</view>
					</view>
				</swiper-item>
				<swiper-item>
					<view class="swiper-item uni-bg-red">
						<image
							src="https://img-blog.csdnimg.cn/2021032902333382.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1dlY2hhdF9WaW5jZXJv,size_16,color_FFFFFF,t_70#pic_center"
							class="big"></image>
						<view class="bottom_item">
							<view class="card">
								<image src="../../static/chain.jpg" class="small"></image>
								<text class="small_text">小丑里的疯子发起 2020 0312</text>
							</view>
							<view class="low">
								<view class="text_low">
									<text style="color: #007c00;">500.0</text>
									<text>金额</text>
								</view>
								<view class="text_low">
									<text>500.0</text>
									<text>金额</text>
								</view>
								<view class="text_low">
									<text>500.0</text>
									<text>金额</text>
								</view>

							</view>
						</view>
					</view>
				</swiper-item>
			</swiper>

		</view>
	</view>
</template>

<script>
	export default {
		
		data() {
			return {
				background: ['color1', 'color2', 'color3'],
				indicatorDots: false,
				autoplay: true,
				interval: 2000,
				duration: 500
			}
		},
		methods: {
			go_acticle: function() {
				console.log('go to acticle')
				uni.navigateTo({
					url: "acticle"
				})
			},

			go_pho: function() {
				uni.makePhoneCall({
					phoneNumber: '189732811132' //仅为示例
				});
			},
			go_for_help: function() {
				uni.navigateTo({
					url: "../give/give"
				})
			},
			changeIndicatorDots(e) {
				this.indicatorDots = !this.indicatorDots
			},
			changeAutoplay(e) {
				this.autoplay = !this.autoplay
			},
			intervalChange(e) {
				this.interval = e.target.value
			},
			durationChange(e) {
				this.duration = e.target.value
			}
		}
	}
</script>

<style>
	page {
		background: linear-gradient(#999999, #336666);
	}

	.small_text {
		font-size: 20rpx;
		line-height: 20rpx;
	}

	.low {
		padding: 0rpx;
		margin: 0rpx;
		display: flex;
		flex-direction: row;
		align-items: center;
		justify-content: center;

	}

	.card {
		display: flex;
		flex-direction: row;
		align-items: center;
	}

	.top_button {
		margin-top: 40rpx;
		background-color: #336666;
		width: 80%;
		height: 100rpx;
		border-radius: 20rpx;
		color: #FFFFFF;
	}

	.text_low {
		display: flex;
		flex-direction: column;
		align-items: center;
		margin: 0rpx 50rpx;
		font-weight: 200;
		padding: 0rpx;
		margin-bottom: 10rpx;
	}

	.all {
		width: 100%;
	}

	.bottom_item {
		display: flex;
		flex-direction: column;

	}

	.swiper-item {
		/* background-color: #000000; */
		color: #000000;
		border-radius: 20rpx;
		/* border:  #999999 1rpx solid; */
		background-color: #FFFFFF;
		/* box-shadow: 60px -16px teal; */
	}

	.big {
		/* background-color: #000000; */
		height: 300rpx;
		width: 100%;
		border-radius: 20rpx;
	}

	.small {
		width: 50rpx;
		height: 50rpx;
		border-radius: 50rpx;
	}

	.swiper {
		/* float: bottom; */
		margin-top: 80rpx;
		height: 650rpx;
	}

	.top_rect {
		padding-top: 30rpx;
		align-content: center;
		text-align: center;
		width: 85%;
		height: 300rpx;
		margin: auto;
		position: relative;
		top: -100rpx;
		border-radius: 20rpx;
		background-color: #FFFFFF;
		/* box-shadow: 2rpx 2px 2px 2px #888888; */
	}

	.bottom_page {
		position: fixed;
		bottom: 0rpx;

		width: 90%;
		height: 70%;
		padding-top: auto;
		background-color: #e4e7e7;
		background-color: #FFFFFF;
		background: rgba(255, 255, 255, 0.63);
		border-radius: 40rpx 40rpx 0rpx 0rpx;
		margin-left: 5%;
		/* 	opacity: 1;
		alpha:0.63 */
	}

	.mid_rect {
		display: flex;
		flex-direction: row;

	}

	.mid_rect view {
		width: 40%;
		height: 100rpx;
		background-color: #FFFFFF;
		border-radius: 10rpx;
		padding: 20rpx;
		margin: auto;
	}
</style>
