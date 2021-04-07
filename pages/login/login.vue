<template>
	<view>
		<view class="top_title">Hi~</view>
		<view class="top_title_two">欢迎你的加入</view>
		<view class="info">
			<view><input type="text" placeholder="请输入手机号码" v-model="username"></view>
			<view><input type="text" placeholder="请输入动态密码" v-model="password"></view>
			<view class="text_finger">录入指纹快速注册</view>
			<view class="image_finger">
				<image src="../../static/finger.jpg" @click="get_finger"></image>
			</view>
		</view>
		
		<button class="button_cl" @click="register">注册账户</button>
		<button class="button_cl" @click ="login">登录</button>
		<button class="button_cl" @click ="go_index">走了</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				isSigner:true,
				username:"",
				password:"",
			}
		},
		methods: {
			go_index:function(){
				uni.switchTab({
					url:"../new_index/new_index"
				})
			}
			,
			login:function(){
				let that = this;
				console.log("login function")
				if(that.isSigner == false){
					uni.showModal({
						title:"没有进行指纹验证",
						showCancel:false
					})
					return 
				}
				uni.request({
					url:"http://localhost:3000/userinfo/login",
					method:'POST',
					data:{
						username:that.username,
						password:that.password
					},
					success:function(res){
						console.log(res.data.login)
						if (res.data.login){
							uni.showModal({
								title:"登录成功",
								showCancel:false
							})
							getApp().globalData.userInfo = res.data.userInfo
							// console.log(res.data)
							console.log(getApp().globalData.userInfo)
						}else{
							uni.showModal({
								title:"密码或者账户不正确或者未注册",
								showCancel:false
							})
							return 
						}
						
						uni.switchTab({
							url:"../new_index/new_index",
							fail() {
								console.log('跳转失败')
							}
						})
					},
					fail:function(){
						console.error("error login")
					}
				})
			}
			,
			register:function(){
				let that = this;
				if(that.isSigner == false){
					uni.showModal({
						title:"没有进行指纹验证",
						showCancel:false
					})
					return 
				}
				uni.request({
					url:"http://localhost:3000/userinfo/register",
					method:'POST',
					data:{
						username:that.username,
						password:that.password
					},
					success:function(res){
						console.log(res.data.register)
						if (res.data.register){
							uni.showModal({
								title:"名字已经被占用哦",
								showCancel:false
							})
							return
						}
						uni.showModal({
							title:"注册成功0",
							showCancel:false
						})	
						uni.switchTab({
							url:"../new_index/new_index",
							fail() {
								console.log('跳转失败')
							}
						})
					},
					fail:function(){
						console.error("error regsiter")
					}
				})
			},
			get_finger: function() {
				let that = this
				uni.checkIsSupportSoterAuthentication({
					success(res) {
						if (res.supportMode) {
							//设备进行指纹识别
							uni.startSoterAuthentication({
								requestAuthModes: ['fingerPrint'],
								challenge: '123456',
								authContent: '请用指纹解锁',
								success(res) {
									console.log(res);
									that.isSigner = true;
									if(res.errCode == 0){
										uni.showModal({
											title:'识别成功',
											showCancel:false
										})
									}
								},
								fail(err) {
									console.log(err);
								},
								complete(res) {
									console.log(res);
								}
							})
						}
					},
					fail(err) {
						console.log(err);
					},
					complete(res) {
					}
				})
			}
		}
	}
</script>

<style>
	page {
		background: linear-gradient(#999999, #336666);
	}

	.top_title {
		padding-top: 220rpx;
		text-align: center;
		font-size: 75rpx;
		color: #FFFFFF;
	}

	.top_title_two {
		padding-top: 15rpx;
		text-align: center;
		font-size: 75rpx;
		color: #FFFFFF;

	}

	.info {
		border-radius: 40rpx;
		width: 80%;
		padding: 60rpx 0rpx;
		background-color: #FFFFFF;
		margin: auto;
		margin-top: 80rpx;
		margin-bottom: 120rpx;
		display: flex;
		flex-direction: column;
		opacity: 0.81;
	}

	input {
		border-bottom: #808080 solid 1rpx;
		padding: 15rpx 30rpx;
		margin: 0rpx 60rpx;
		height: 50rpx;
	}

	.text_finger {
		padding: 40rpx 30rpx;
		margin: 0rpx 60rpx;
		height: 50rpx;
		color: #686868;
	}

	image {
		height: 100rpx;
		width: 100rpx;
	}

	.image_finger {
		text-align: center;
	}

	.button_cl {
		margin: auto;
		margin: 40rpx auto;
		border-radius: 20rpx;
		background-color: #FFFFFF;
		color: #686868;
		width: 50%;
		opacity: 0.7;
	}
</style>
