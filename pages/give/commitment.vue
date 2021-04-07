<template>
	<view>
		<!-- <view class="top_loop">
			<view class="one_split_stop">基本信息</view>
			<view class="one_split_stop">求助说明</view>
			<view class="one_split_stop">医疗证明</view>
			<view class="one_split">经济状况</view>
			<view class="one_split_stop">生成专钥</view>
			
		</view> -->

		<view class="info">
			<label for="who">筹款验证</label>
			<button class="button_sex">银 行 验 证</button>
			<button class="button_sex">医 院 验 证</button>
			<button class="button_sex">其 他 机 构 验 证</button>
			<!-- <input name="who" type="text" placeholder="王"/>
			<label for="what">患者所患有疾病</label>
			<input name="what" type="text" placeholder="王"/> -->
		</view>
		<view class="info">
			<label for="name">你的名字</label>
			<br>
			<view>1. 所发起的个人大病求助项目，全部求助款项将用于求助人的治疗及康复费用，绝不挪用，如有剩余及时退还。
				<br>
				2. 所发布的求助信息完整、准确、真实、及时、合法，无虚构或隐瞒情形。
				<br>
				3. 将尊重赠与人的意愿，严格按照平台要求，及时说明求助人的治疗花费、家庭经济状况等平台要求说明的情况，并公示相应证明材料。
				<br>
				4.本筹款行为已经过银行、医院和其他第三方机构（如居委会、街道办、公益组织等能提供高可信度信息的机构或组织）三者之一的权威验证。

				若有违反，承担全部法律责任，并赔偿相关方所有损失。</view>
			<br>
			<!-- <input name="name" type="text" placeholder="王"/>
			<label for="pho">你的电话号码</label>
			<input name="pho" type="text" placeholder="王"/> -->
		</view>

		<button class="next_step_but" @click="next_step">我同意此承诺</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {

			}
		},
		methods: {
			next_step: function() {
				uni.navigateTo({
					url: "tran_info"
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

	.button_sex {
		width: 80%;
		height: 100rpx;
		background-color: #D0D0D0;
		margin-top: 10rpx;
		color: #FFFFFF;
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

	.info view {
		width: 80%;
		margin: auto;
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

	.next_step_but {
		margin-top: 100rpx;
		background-color: #5A9298;
		border-radius: 20rpx;
		height: 100rpx;
		width: 75%;
		color: #FFFFFF;
	}

	label {

		padding: 50rpx;
		color: #686868;
	}
</style>
