<template>
	<view v-if="!hasLogin">
	</view>
	<view class="container" v-else>
		<u-row>
			<u-col span="12" justify="center">
				<u--text :text="user.name" align="center" size="25"></u--text>
			</u-col>
		</u-row>
		<u-row>
			<u-col span="12">
				<view style="height: 10px;"></view>
			</u-col>
		</u-row>
		<u-row>
			<u-col span="12">
				<u-cell-group>
					<u-cell title="我的余额" isLink @click="jumpToWallet(1)" />
					<u-cell title="我的订单" isLink @click="jumpToOrder(1)" />
					<u-cell title="我的预约" isLink @click="jumpToAppointment(1)" />
				</u-cell-group>
			</u-col>
		</u-row>
		<u-row>
			<u-col span="12">
				<view style="height: 10px;"></view>
			</u-col>
		</u-row>
		<u-row>
			<u-col span="12">
				<u-button type="error" :plain="true" text="退出登录"></u-button>
			</u-col>
		</u-row>
	</view>
</template>


<script>
	export default {
		data() {
			return {
				hasLogin: true,
				user: {
					name: "昵称",
					avatar: "https://yuyuzheng.cn:8234/upload/YQ125602691000574341.png",
				}
			}
		},
		methods: {
			jumpToWallet(userId) {
				uni.navigateTo({
					url: '/pages/user/wallet'
				})
			},
			jumpToOrder(userId) {
				uni.navigateTo({
					url: '/pages/user/order'
				})
			},
			jumpToAppointment(userId) {
				uni.navigateTo({
					url: '/pages/user/appointment'
				})
			}
		},
		mounted() {}
	}
</script>

<style>
	* {
		box-sizing: border-box;
	}

	.container {
		margin: 10px 8px;
	}

	.avatar-row {
		display: flex;
		justify-content: center;
		align-items: center;
	}

	.avatar-col {
		display: flex;
		justify-content: center;
	}
</style>