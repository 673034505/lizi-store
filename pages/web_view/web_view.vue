<template>
	<view>
		<!-- web-view 使用列子 -->
		<web-view  :src="url"  :webview-styles="webviewStyles" v-if="url.length>0" ></web-view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				url:'',
				webviewStyles: {
					progress: false,
				},
				id:''
			};
		},
		onLoad(options) {
			if (options && options.id) {//如果需要传值，用值拼接
				this.id = options.id
			}
			 this.id = 100
			 let _self = this;
			uni.getSystemInfo({
			    success: function (res) {
					//动态设置屏幕高度和宽度
					_self.url = `/hybrid/html/user.html?pageW=${res.windowWidth}&id=${_self.id}`
			    }
			});
		},
	}
</script>

<style lang="less">

</style>
