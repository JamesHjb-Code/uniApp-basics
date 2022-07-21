<template>
	<view id="myId">
		这是test组件{{num}}
	</view>
</template>

<script>
	export default {
		data() {
			return {
				num:3
			}
		},
		beforeCreate(){
			console.log('实例已经开始初始化了')
			console.log('beforeCreate',this.num)
		},
		created(){
			console.log('created',this.num)
		},
		beforeMount(){
			console.log('beforeMount',document.getElementById('myId'))
		},
		mounted(){
			console.log('mounted',document.getElementById('myId'))
		},
		methods: {
			
		}
	}
</script>

<style>

</style>
