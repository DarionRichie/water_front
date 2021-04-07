<template>
	<view>
		<swiper class="swiper" :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval"
			:duration="duration">
			<swiper-item>
				<view class="swiper-item">
					<image src="https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fimage.shumiao.net%2Fuploads%2F20190222%2F18%2F1550830681-CKhAwQBoTZ.jpg&refer=http%3A%2F%2Fimage.shumiao.net&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=jpeg?sec=1619363803&t=ca39df5143247692c05a4e21fab44271"></image>
				</view>
			</swiper-item>
			<swiper-item>
				<view class="swiper-item">
					<image src="https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fk.zol-img.com.cn%2Fdcbbs%2F15383%2Fa15382750_s.jpg&refer=http%3A%2F%2Fk.zol-img.com.cn&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=jpeg?sec=1619363803&t=0982197303cee08eee635289787d802d"></image>
				</view>
			</swiper-item>
			<swiper-item>
				<view class="swiper-item">
					<image src="https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fimg1.juimg.com%2F150524%2F330718-15052422132978.jpg&refer=http%3A%2F%2Fimg1.juimg.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=jpeg?sec=1619363803&t=8a4bbc5c3df9d6c98f2a6fc0fccc45d3"></image>
				</view>
			</swiper-item>
		</swiper>
		<view class="acticle_list" @click="go_toActicle">
			<view class="list_Top">
				<image src="../../static/chain.jpg"></image>
				<text>wehelp</text>
			</view>
			<image class="acticle_pic" src="https://img0.baidu.com/it/u=248176870,4282818294&fm=26&fmt=auto&gp=0.jpg"></image>
			<view class="list_Bottom">
				<text>wehelp</text>
			</view>
		</view>
		
		<view class="acticle_list" @click="go_toActicle">
			<view class="list_Top">
				<image src="../../static/chain.jpg"></image>
				<text>wehelp</text>
			</view>
			<image class="acticle_pic" src="https://img0.baidu.com/it/u=248176870,4282818294&fm=26&fmt=auto&gp=0.jpg"></image>
			<view class="list_Bottom">
				<text>wehelp</text>
			</view>
		</view>
		
		
		<view class="acticle_list" @click="go_toActicle">
			<view class="list_Top">
				<image src="../../static/chain.jpg"></image>
				<text>wehelp</text>
			</view>
			<image class="acticle_pic" src="https://img0.baidu.com/it/u=248176870,4282818294&fm=26&fmt=auto&gp=0.jpg"></image>
			<view class="list_Bottom">
				<text>wehelp</text>
			</view>
		</view>
		
		<view class="acticle_list" @click="go_toActicle">
			点击查看推文
		</view>
		
		<view class="acticle_list_sos" @click="playMusic">
			发起求救
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				indicatorDots: true,
				autoplay: true,
				interval: 2000,
				duration: 500
			}
		},
		methods: {
			go_toActicle: function() {
				uni.navigateTo({
					url: "../acticle/acticle"
				})
			},
			playMusic: function() {
				const innerAudioContext = uni.createInnerAudioContext();
				innerAudioContext.autoplay = true;
				innerAudioContext.src = 'http://d.datouwang.com/uploads/file/yinxiao/2019/yinxiao2474.mp3';
				innerAudioContext.onPlay(() => {
					console.log('开始播放');
				});
				innerAudioContext.onError((res) => {
					console.log(res.errMsg);
					console.log(res.errCode);
				});
			}
		}
	}
</script>

<style>
	.acticle_list {

		background-color: #FFFFFF;
		width: 95%;
		/* height: 100rpx; */
		border-radius: 20rpx;
		margin: auto;
		/* line-height: 100rpx; */
		/* padding-left: 20rpx; */
		margin-top: 20rpx;
	}
	
	.swiper {
		width: 100%;
		height: 450rpx;
	}

	.swiper-item {
		background-color: #000000;
	}
	.swiper-item image{
		width: 100%;
	}
	.acticle_pic{
		width: 100%;
		height: 400rpx;
		margin-bottom: 0rpx;
		display:block;
	}
	.acticle_list_sos {
		background-color: #ff0000;
		width: 85%;
		height: 100rpx;
		border-radius: 20rpx;
		margin: auto;
		line-height: 100rpx;
		padding-left: 20rpx;
		margin-top: 20rpx;
	}
	.list_Top{
		border-radius: 20rpx 20rpx 0rpx 0rpx;
		height: 100rpx;
		background-color: #333333;
		display: flex;
		flex-direction: row;
		align-items: center;
		padding-left: 50rpx;
	}
	.list_Bottom{
		border-radius: 0rpx 0rpx 20rpx 20rpx;
		height: 100rpx;
		background-color: #333333;
		display: flex;
		flex-direction: row;
		align-items: center;
		padding-left: 50rpx;
		margin-top: 0rpx;
	}
	.list_Top image{
		width: 75rpx;
		height: 75rpx;
		border-radius: 150rpx;
	}
	.list_Top text{
		padding: 20rpx;
		color: #FFFFFF;
		opacity: 0.7;
	}
	page {
		background-color: #ebebeb;
	}
</style>
