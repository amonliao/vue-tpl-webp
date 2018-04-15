# vue-webpack-webp模板

> index.html 自动引入百度统计、flexible、vConsole

> 添加对webp支持（可不选，如果项目没有涉及大图或者不需要优化）


基于 vue 2 封装出的 Image 组件，重写img，目的支持webp， 优化图片，提高移动端性能。

### 支持

- 支持lazyload
- 支持webp接入，兼容webp则使用指定规则的webp，不兼容则使用默认图
- 提供webpPlugin，可方便的接入其他第三方库，从而良好的引入webp

### Usage

```example
<style>
.img{
    width: 100px;
    height: 100px;
    margin:10px;
    display: block;
}
</style>
<template>
    <Images v-for="img in imgs" class="img" :src="img" />
    <Images v-for="img in imgs" class="img" lazy :src="img" />
</template>
<script>
    export default {
        data(){
            return {
                imgs: [
                    require('assets/logo.png')
                ]
            }
        }
    }
</script>
```

