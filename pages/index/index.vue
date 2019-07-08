<template>
	<view class="content">
		<image class="logo" src="/static/logo.png"></image>
		<text class="payment-text" @click="togglePayment()">显示支付弹窗</text>
		<best-payment-password :show="payFlag" :forget="true" :value="paymentPwd" digits="6" @submit="checkPwd" @cancel="togglePayment"></best-payment-password>
	</view>
</template>

<script>
	import bestPaymentPassword from '../../components/best-payment-password/best-payment-password.vue'
	export default {
		data() {
			return {
				payFlag: false,
				paymentPwd: '' //可以写默认值
			}
		},
		components: {
			bestPaymentPassword
		},
		onLoad() {

		},
		methods: {
			togglePayment() {
				this.payFlag = !this.payFlag;
			},
			checkPwd: function(e) {
				console.log(e)
				// 这里是写验证密码的业务逻辑,比如密码错误可以在这边清空
				this.paymentPwd = '';
			}
		}
	}
</script>

<style>
	.content {
		width: 100%;
		/* #ifdef H5 */
		min-height: calc(100vh - var(--window-bottom) - var(--window-top));
		/* #endif */
		/* #ifndef H5 */
		min-height: 100vh;
		/* #endif */
		background-color: #fff;
		padding-top: 150upx;
	}

	.logo {
		height: 400upx;
		width: 400upx;
		display: block;
		margin: 0 auto;
	}

	.payment-text {
		text-align: center;
		width: 240upx;
		line-height: 70upx;
		display: inline-block;
		border: 1px solid #26C6B3;
		font-size: 28upx;
		border-radius: 10upx;
		color: #26C6B3;
		position: absolute;
		left: 50%;
		margin-left: -120upx;
		bottom: 250upx;
	}
</style>
