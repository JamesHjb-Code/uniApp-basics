<template>
	<view>
		<view>这是列表项</view>
		<view v-for="item in list">{{item}}</view>
		<button @click="handleRefresh()">点击下拉刷新</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list:['java','html','javascript']
			}
		},
		// 触发了刷新数据
		onPullDownRefresh(){
			console.log('触发了刷新')
			setTimeout(()=>{
			this.list = ['java','javascript','python','go']
				uni.stopPullDownRefresh()
			},2000)
		},
		methods: {
			// 点击函数
			handleRefresh(){
				// 开始下拉刷新，调用后触发下拉刷新动画，效果与用户手动下拉刷新一致
				uni.startPullDownRefresh()
			}
		}
	}
</script>

<style>

</style>
