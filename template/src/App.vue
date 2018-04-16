<template>
  <div id="app">
    <img src="./assets/logo.png">
    {{#webp}}
    <Images :src="img" webp lazy/>
    {{/webp}}
    {{#router}}
    <router-view/>
    {{else}}
    <HelloWorld/>
    {{/router}}
  </div>
</template>

<script>
{{#unless router}}
import HelloWorld from './components/HelloWorld'

{{/unless}}
{{#webp}}
const img = require("./assets/logo.png");

{{/webp}}
export default {
  name: 'App'{{#router}}{{else}},
  components: {
    HelloWorld
  }{{/router}}{{#webp}},
  data() {
    return {
      img,
    };
  },{{/webp}}
}
</script>

<style>
#app {
  font-family: "Helvetica Neue"
  , Helvetica, Arial, "PingFang SC", "Hiragino Sans GB",
   "Heiti SC", "Microsoft YaHei", "WenQuanYi Micro Hei", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
