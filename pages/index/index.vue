<template>
	<view class="content">
		<test-import></test-import>
		<uni-badge text="1"></uni-badge>
		<uni-badge text="2" type="success" @click="bindClick"></uni-badge>
		<uni-badge text="3" type="primary" :inverted="true"></uni-badge>
		<uni-calendar ref="calendar" :insert="false" @confirm="confirm" />
		<button @click="open">打开日历</button>
	</view>
</template>

<script>
	import testImport from '../../components/test.vue'
	export default {
		components: {
			testImport
		},
		data() {
			return {
				title: 'Hello'
			}
		},
		onLoad(options) {
			console.log('加载完成了', options)
		},
		onShow() {
			console.log('页面显示了')
		},
		onReady() {
			console.log('页面初次渲染完成了')
		},
		onHide() {
			console.log('页面隐藏了')
		},
		methods: {
			open() {
				this.$refs.calendar.open();
			},
			confirm(e) {
				console.log(e);
			}
		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>
