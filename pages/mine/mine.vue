<template>
	<view>
		<view class="top_userInfo">
			<view class="head_png"><image src="../../static/kfc.jpg"></image></view>
			<view>
				<view style="font-weight: bold;">{{userInfo.username}}</view>
				<view></view>
			</view>
		</view>
		
		<view class="middle">
			<view class="middle_list">
				<image src="../../static/online.png" style="width: 80rpx;height: 80rpx;margin-bottom: 20rpx;"></image>
				<view>在线咨询</view>
			</view>
			<view class="middle_list">
				<image src="../../static/mygive.png" style="width: 80rpx;height: 80rpx;margin-bottom: 20rpx;"></image>
				<view>我的筹款</view>
			</view>
		</view>
		<!-- <view>
			{{userInfo.username}}
		</view> -->
		<view class="button_bottom">
			<view style="height: 150rpx;"></view>
			<view class="list_element">
				<image src="../../static/note.png"></image>
				<view>捐赠记录</view>
			</view>
			<view class="list_element">
				<image src="../../static/step.png"></image>
				<view>捐赠跟进</view>
			</view>
			<view class="list_element">
				<image src="../../static/chatroom.png"></image>
				<view>捐赠群聊</view>
			</view>
			<view class="list_element">
				<image src="../../static/use.png"></image>
				<view>如何进行链筹使用</view>
			</view>
			<view class="list_element" @click="exit">
				<image src="../../static/exit.png"></image>
				<view>退出登录</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				userInfo:getApp().globalData.userInfo
			}
		},
		methods: {
			exit:function(){
				uni.navigateTo({
					url:"../login/login"
				})
			}
		}
	}
</script>

<style>
	page{
		background: linear-gradient(#999999, #336666);
		opacity: 1;
	}
	image{
		width: 200rpx;
		height: 200rpx;
	}
	.middle_list{
		display: flex;
		flex-direction: column;
		align-items: center;
		margin: auto;
	}
	.middle{
		background-color: #FFFFFF;
		width: 85%;
		height: 300rpx;
		margin: auto;
		border-radius: 40rpx;
		position: relative;
		top: 100rpx;
		display: flex;
		flex-direction: row;
		align-items: center;
	}
	.head_png{
		margin-left: 30rpx;
		/* text-align: center; */
	}
	.button_bottom{
		display: flex;
		flex-direction: column;
		position: fixed;
		bottom: 0rpx;
		height: 60%;
		width: 100%;
		background-color: rgba(255,255,255,0.7);
		border-radius: 60rpx 60rpx 0rpx 0rpx;
		z-index: -1;
	}
	.list_element image{
		width: 70rpx;
		height: 70rpx;
		margin-right: 40rpx;
	}
	.top_userInfo{
		display: flex;
		flex-direction: row;
		margin-top: 105rpx;
		align-items: center;
	}
	.list_element{
		display: flex;
		flex-direction: row;
		align-items: center;
		border-radius: 20rpx;
		background-color: #FFFFFF;
		opacity: 1;
		width: 80%;
		height: 100rpx;
		line-height: 100rpx;
		margin: 20rpx auto;
		padding-left: 50rpx;
		color: #000000;
		font-weight: bold;
		box-shadow: 1rpx 1rpx 1rpx 1px #C0C0C0;
	}
</style>
