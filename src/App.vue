<template>
  <div id="app">
    <p>{{ message }}</p>
    <p>{{ count }}</p>
    
    <button v-on:click="messageChange('男')">男</button>
    <button v-on:click="messageChange('女')">女</button>
    <button v-on:click="messageChange('？？？')">どちらでもない</button>
    </br></br>
    <button v-on:click="countChange(1)">（不正）カウントを追加</button>
    </br></br>
    <div style="width: 100%; height:2px; background-color: black;"></div>
    </br>
    <input v-model="store.message" name="message" placeholder="商品名をここに入力">
    <input v-model="store.value" type="number" name="value" value=1000 placeholder=1000 step=100 max=10000 min=100 style="width: 80px">
    <button v-on:click="arrivalProduct(store.message,store.value)">登録</button>
    </br></br>
    <button v-on:click="resetProduct()">商品すべて破棄</button>
    <ul>
      <li v-for="item in store" style="display: inherit; text-align:left;">
        {{ item.message }}
        {{ item.value }}円
      </li>
    </ul>
    </br></br>
    <div style="width: 100%; height:2px; background-color: black;"></div>
    </br>

  </div>
</template>

<script>

export default {
  el: "#app",
  data() {
    return {
       message: "君は女の子かな？それとも男の子かな？",
       count: 0,
       store: [
         {
           message: "高級じゃない腕時計",
           value: 900
         },
         {
           message: "スクラップ（鉄くず）",
           value: 1700
         },
         {
           message: "期限切れのチケット",
           value: 10
         },
       ],
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
    },
    arrivalProduct: function(message,value) {
      var product = {};
      
      product['message'] = message;
      product['value'] = value;
      this.store.push(product);
    },
    resetProduct: function() {
      this.store = [];
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
