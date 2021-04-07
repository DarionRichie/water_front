<template>
	<view>
		<view class="top_loop">
			<view class="one_split_stop">基本信息</view>
			<view class="one_split_stop">求助说明</view>
			<view class="one_split_stop">医疗证明</view>
			<view class="one_split">经济状况</view>
			<view class="one_split_stop">生成专钥</view>
			
		</view>
		
		<view class="info">
			<label for="who">车产</label>
			<input name="who" type="text" placeholder="王"/>
			<label for="what">患者所患有疾病</label>
			<input name="what" type="text" placeholder="王"/>
		</view>
		<view class="info">
			<label for="name">房产</label>
			<input name="name" type="text" placeholder="王"/>
			<label for="pho">你的电话号码</label>
			<input name="pho" type="text" placeholder="王"/>
		</view>
		<view class="info">
			<label for="name">家庭年收入</label>
			<input name="name" type="text" placeholder="王"/>
			<label for="pho">你的电话号码</label>
			<input name="pho" type="text" placeholder="王"/>
		</view>
		<view class="info">
			<label for="name">负债情况</label>
			<input name="name" type="text" placeholder="王"/>
			<label for="pho">你的电话号码</label>
			<input name="pho" type="text" placeholder="王"/>
		</view>
		<view class="info">
			<label for="name">治疗已花费金额</label>
			<input name="name" type="text" placeholder="王"/>
			<label for="pho">你的电话号码</label>
			<input name="pho" type="text" placeholder="王"/>
		</view>
		<view class="info">
			<label for="name">投保情况</label>
			<input name="name" type="text" placeholder="王"/>
			<label for="pho">你的电话号码</label>
			<input name="pho" type="text" placeholder="王"/>
		</view>
		<button class="next_step_but" @click="next_step">下一步</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {

			}
		},
		methods: {
			next_step:function(){
				uni.navigateTo({
					url:"tran_info"
				})
			}
		}
	}
</script>

<style>
	page {
		background: linear-gradient(#999999, #336666);
	}
	.top_loop{
		margin-top: 40rpx;
		display: flex;
		flex-direction: row;
		justify-content: center;
		
	}
		
	.one_split{
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
	.one_split_stop{
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
	.info{
		width: 80%;
		height: 400rpx;
		border-radius: 40rpx;
		background-color: #FFFFFF;
		margin: auto;
		opacity: 0.7;
		margin-top: 40rpx;
		padding-top: 30rpx;
	}
	.next_step_but{
		margin-top: 100rpx;
		background-color: #5A9298;
		border-radius: 20rpx;
		height: 100rpx;
		width: 75%;
		color: #FFFFFF;
	}
	label{
		
		padding: 50rpx;
		color: #686868;
	}
</style>
