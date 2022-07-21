<template>
	<view>
	<view>
		导航跳转的学习
	</view>
	<navigator url="/pages/detail/detail?id=80&age=22">跳转到详情页</navigator>
	<navigator url="/pages/message/message" open-type="switchTab">跳转到tabBar信息页</navigator>
	<navigator url="/pages/detail/detail" open-type="redirect">跳转到详情页</navigator>
	<button @click="goDetail">跳转之详情页</button>
	<button @click="goMessage">跳转之信息页</button>
	<button type="primary" @click="redirectMessage">跳转之详情页</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		onUnload(){
			console.log('该页面卸载了！')
		},
		methods: {
			goDetail(){
				uni.navigateTo({
					url:'/pages/detail/detail?id=80&age=25'
				})
			},
			goMessage(){
				uni.switchTab({
					url:'/pages/message/message'
				})
			},
			redirectMessage(){
				uni.redirectTo({
					url:'/pages/detail/detail'
				})
			}
		}
	}
</script>

<style>

</style>
