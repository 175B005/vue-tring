<template>
  <div id="app">
    https://laraweb.net/surrounding/4467/
    <p>{{ message }}</p>
    <p>{{ count }}</p>
    
    <button v-on:click="messageChange('PHPのフレームワークといえばLaravel！')">「PHP」が好き</button>
    <button v-on:click="messageChange('JavaScriptのライブラリといえばVue.js！')">「JavaScript」が好き</button>
    </br>
    <button v-on:click="countChange(1)">カウントを追加</button>
  </div>
</template>
<script>
export default {
  el: "#app",
  data() {
    return {
       message: "好きな言語は？",
       count: 0,
    };
  },
  methods: {
    messageChange: function(lang) {
      if(this.message !== lang){
        this.message = lang;
        this.countChange(-this.count);
      }
      else{
        this.countChange(1);
      }
    },
    countChange: function(add) {
      this.count += add;
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
