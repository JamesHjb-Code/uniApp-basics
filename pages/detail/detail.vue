<template>
	<!-- <view>
		<view class="box2" hover-class="active-box2">
			<view class="box" hover-class="active-box" :hover-start-time="2000" :hover-stay-time="2000"
				:hover-stop-propagation="true">我是一名篮球爱好者</view>
		</view>
	</view> -->
	<view>
		<button>按钮</button>
		<button size="mini">按钮</button>
		<button type="primary">按钮</button>
		<button plain>按钮</button>
		<button disabled>按钮</button>
		<button loading></button>
		<image src="http://destiny001.gitee.io/image/cxk.gif"></image>
		<image src="http://destiny001.gitee.io/image/cxk.gif" mode="aspectFit"></image>
		<image src="http://destiny001.gitee.io/image/cxk.gif" mode="aspectFill"></image>
	</view>
	
</template>

<script>
	export default {
		data() {
			return {

			}
		},
		methods: {

		}
	}
</script>

<style>
	.box {
		width: 100px;
		height: 100px;
		background: aqua;
	}

	.active-box {
		background: blue;
	}

	.box2 {
		width: 200px;
		height: 200px;
		background: #d3d3d3;
	}

	.active-box2 {
		background: green;
	}
</style>
