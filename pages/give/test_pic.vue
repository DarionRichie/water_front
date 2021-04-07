<template>
    <zh-upFile 
        :config='config' 
        :type='1' 
        width='290rpx'
        height='180rpx'
        @fileListChange='upImgZ'></zh-upFile>
</template>
<script>
	import zhUpFile from '@/components/zh-upFile'
    export default {
        data() {
            return {
                config:{
                    count:1,                                    // 上传图片张数
                    sizeType: ['original','compressed'],                // original 原图，compressed 压缩图，默认二者都有
                    sourceType: ['album','camera'],                             // album 从相册选图，camera 使用相机，默认二者都有。如需直接开相机或直接选相册，请只使用一个选项
                },
            }
        },
        components:{
            'zh-upFile':zhUpFile
        },
        methods:{
            upImgZ(data){
                console.log(data)
            },
        }
    }
	
</script>