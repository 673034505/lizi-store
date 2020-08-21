
<template>
         <view class="container">
		
          </view>
</template>
<script>
    export default {
        data() {
            return {
				
            }
        },
		onLoad() {
			setTimeout(function(){
				//关闭启动界面。app端才会执行 其他不执行
                // #ifdef  APP-PLUS  
                    plus.navigator.closeSplashscreen() 
                // #endif
			},3000)
		},
        methods: {
			
        },
    }
</script>
<style>
    
</style>