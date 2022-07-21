<template>
	<view>
		<button type="primary" @click="chooseImg">上传图片</button>
		<image v-for="item in imgArr" :src="item" @click="previewImage(item)"></image>
		
		<!-- 跨域条件编译 -->
		<!-- #ifdef H5 -->
		<view>我希望只在h5页面中看见</view>
		<!-- #endif -->
		<!-- #ifdef MP-WEIXIN -->
		<view >
			我希望只在微信小程序中看见
		</view>
		<!-- #endif -->
	</view>
</template>

<script>
	export default {
		data() {
			return {
				imgArr:[]
			}
		},
		onLoad(){
			//#ifdef H5
			console.log('我希望看见在h5页面')
			//#endif
			//#ifdef MP-WEIXIN
			console.log('我希望看见在微信小程序')
			//#endif
		},
		methods: {
			chooseImg(){
				uni.chooseImage({
					count:6,
					success:res=>{
						console.log(res)
						this.imgArr = res.tempFilePaths
					}
				})
			},
			previewImage(currentImg){
				uni.previewImage({
					urls:this.imgArr
				})
			}
		}
	}
</script>

<style>
/* h5样式 */
/* #ifdef H5 */
view{
	background-color:honeydew;
}
/* #endif */
/* 小程序样式 */
/* #ifdef  MP-WEIXIN*/
view{
	background-color:#000;
}
/* #endif */
</style>
