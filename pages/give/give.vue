<template>
	<view>
		<view class="top_loop">
			<view class="one_split">基本信息</view>
			<view class="one_split_stop">求助说明</view>
			<view class="one_split_stop">医疗证明</view>
			<view class="one_split_stop">经济状况</view>
			<view class="one_split_stop">生成专钥</view>

		</view>

		<view class="info">
			<label for="who">你为谁捐款</label>
			<input name="who" type="text" placeholder="王" v-model="who" />
			<label for="what">患者所患有疾病</label>
			<input name="what" type="text" placeholder="王" v-model="disease" />
		</view>
		<view class="info">
			<label for="name">你的名字</label>
			<input name="name" type="text" placeholder="王" v-model="name" />
			<label for="pho">你的电话号码</label>
			<input name="pho" type="text" placeholder="王" v-model="phoneNumber" />
		</view>

		<button class="next_step_but" @click="next_step">下一步</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				who: "",
				disease: "",
				name: "",
				phoneNumber: ""
			}
		},
		methods: {
			next_step: function() {
				let that = this;
					
				if (that.who != "" && that.disease != "" && that.name != "" &&that.phoneNumber != ""){
					
				}else{
					uni.showModal({
						showCancel:false,
						title:"不能为空哦"
					})
					return
				}
				uni.setStorage({
					key: 'who',
					data: that.who,
					success: function() {
						// console.log('success');
					}
				})
				uni.setStorage({
					key: 'disease',
					data: that.disease,
					success: function() {
						// console.log('success');
					}
				})
				uni.setStorage({
					key: 'name',
					data: that.name,
					success: function() {
						// console.log('success');
					}
				})
				uni.setStorage({
					key: 'phoneNumber',
					data: that.phoneNumber,
					success: function() {
						// console.log('success');
					}
				})
				uni.navigateTo({
					url: "info_forhelp"
				})
			}
		}
	}
</script>

<style>
	page {
		background: linear-gradient(#999999, #336666);
	}

	.top_loop {
		margin-top: 40rpx;
		display: flex;
		flex-direction: row;
		justify-content: center;

	}

	.one_split {
		width: 15%;
		height: 50rpx;
		border-radius: 20rpx;
		background-color: #5A9298;
		margin: 5rpx;
		text-align: center;
		line-height: 50rpx;
		font-size: 20rpx;
		color: #FFFFFF;
	}

	.next_step_but {
		margin-top: 100rpx;
		background-color: #5A9298;
		border-radius: 20rpx;
		height: 100rpx;
		width: 75%;
		color: #FFFFFF;
	}

	.one_split_stop {
		width: 15%;
		height: 50rpx;
		border-radius: 20rpx;
		background-color: #94ADB0;
		margin: 5rpx;
		text-align: center;
		line-height: 50rpx;
		font-size: 20rpx;
		color: #808080;
	}

	input {
		/* border: #808080 solid 20rpx; */
		border-radius: 20rpx;
		padding: 15rpx 30rpx;
		margin: 0rpx 60rpx;
		margin-top: 10rpx;
		height: 50rpx;
		background-color: #D0D0D0;
		margin-bottom: 20rpx;
	}

	.info {
		width: 80%;
		height: 400rpx;
		border-radius: 40rpx;
		background-color: #FFFFFF;
		margin: auto;
		opacity: 0.7;
		margin-top: 40rpx;
		padding-top: 30rpx;
	}

	label {

		padding: 50rpx;
		color: #686868;
	}
</style>
