<template>
  <div id="app">
    https://laraweb.net/surrounding/4467/
    <p>@{{ message }}</p>
    
    <button v-on:click="messageChange('PHPのフレームワークといえばLaravel！')">「PHP」が好き</button>
    <button v-on:click="messageChange('RubyのフレームワークといえばRails！')">「Ruby」が好き</button>
    <button v-on:click="messageChange('JavaScriptのライブラリといえばVue.js！')">「JavaScript」が好き</button>
  </div>
</template>
<script>
export default {
  el: "#app",
  data() {
    return { message: "好きな言語は？" };
  },
  methods: {
    messageChange: function(lang) {
      this.message = lang;
    }
  }
};
</script>
<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
