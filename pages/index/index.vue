<template>
	<view class="content">
		<image class="logo" src="/static/logo.png"></image>
		<view class="text-area">
			<text class="title">{{title}}</text>
		</view>
		
		<button @click="to_share">分享例子</button>
		<button @click="mine">个人页面</button>
		<button @click="chain">导航页面</button>
		<button @click="index">首页页面</button>
		<button @click="acticle">文章页面</button>
		<button @click="give">筹款页面</button>
		<button @click="denote">捐赠页面</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello'
			}
		},
		onLoad() {

		},
		methods: {
			to_share:function(){
				uni.navigateTo({
					url:"../login/login"
				})
			},
			mine:function(){
				uni.switchTab({
					url:"../mine/mine"
				})
			},
			acticle:function(){
				uni.navigateTo({
					url:"../acticle_list/acticle_list"
				})
			},
			chain:function(){
				uni.navigateTo({
					url:"../navition/navition"
				})
			},
			index:function(){
				uni.switchTab({
					url:"../new_index/new_index"
				})
			},
			give:function(){
				uni.navigateTo({
					url:"../give/give"
				})
			},
			denote:function(){
				uni.navigateTo({
					url:"../denote/denote"
				})
			}
		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		
		
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>
