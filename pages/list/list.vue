<template>
	<view>
		<view>这是列表项</view>
		<button type="primary" @click="setStorage">存储数据</button>
		<button type="primary" @click="getStorage">获取数据</button>
		<button type="primary" @click="removeStorage">移除数据</button>
		<view v-for="item in list" class="box-item">{{item}}</view>
		<!-- <button @click="handleRefresh()">点击下拉刷新</button> -->
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list:['java','html','javascript','java','html','javascript','java','html','javascript','javascript','java','html','javascript']
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
		onReachBottom(){
			console.log('触发了上拉刷新')
			const cityList = ['广州','深圳','珠海','end']
			this.list=[...this.list,...cityList]
		},
		methods: {
			// 点击函数
			handleRefresh(){
				// 开始下拉刷新，调用后触发下拉刷新动画，效果与用户手动下拉刷新一致
				uni.startPullDownRefresh()
			},
			setStorage(){
				uni.setStorage({
					key:'data',
					data:{name:'user',pwd:123},
					success(){
						console.log('存储成功')
					}
				})
			},
			getStorage(){
				uni.getStorage({
					key:'data',
					success(res){
						console.log('获取成功',res.data)
					}
				})
			},
			removeStorage(){
				uni.removeStorage({
					key:'data',
					success(){
						console.log('删除成功！')
					}
				})
			}
		}
	}
</script>

<style lang="scss" scoped>
.box-item{
	height:100px;
}
</style>
