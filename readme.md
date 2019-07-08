# 本套代码是uni-app框架所写
	本组件在任意Vue框架下可用
	
## 类似于支付宝输入支付密码的弹窗

> 引入组件

```
	//引入组件文件
	import bestPaymentPassword from '../../components/best-payment-password/best-payment-password.vue'

	//声明组件
	export default {
		components:{
			bestPaymentPassword
		}
	}
```

> 使用组件

```
	//以下是该组件使用的全部属性
	<best-payment-password :show="payFlag" :value="paymentPwd" digits="6" @submit="checkPwd" @cancel="togglePayment"></best-payment-password>
```

> 属性说明

属性 | 类型 |  默认值 | 说明
:-:|:-:|:-:|-
show | Boolean | false | 控制显示跟隐藏
value | String | 无 | 密码输入的默认值
digits | [String,Number] | 6 | 密码输入是位数（最多7位）
forget | Boolean | true | 是否显示忘记密码（忘记密码跳转地址自己进去里面填）

> 事件说明

事件名称 | 说明
:-:|-
submit | 输入密码到指定位数（就是等于digits的值）的时候自动触发的函数
cancel | 弹窗取消按钮（点击阴影处会自动关闭弹窗）

