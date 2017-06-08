<template>
  <div id="app">
    <transform v-on:WTtranslate="serverCall"></transform>
    <transout v-bind:text="msg"></transout>
    <div class="container">
      <p class='is-pulled-right'>powered by Yandex Api:<a target='_blank' href='http://translate.yandex.com/'>yandex transtaler</a></p>

    </div>
  </div>
</template>

<script>

import transform from './components/translaterform.vue'
import transout from './components/translaterout.vue'
export default {

  name: 'app',
  data () {
    return {
      msg:''
    }
  },
  components:{
    transform,
    transout
  },
  methods:{

    serverCall:function(text,lang){
      this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20170606T130506Z.569d04f822ca5bb7.e99ec451b3d74194f094e10cb21624aed26d3e9a&text='+text+'&lang='+lang)
      .then(function(response,error){
        //passing the requested text to the msg variable
        this.msg=response.body.text[0];

    })
   }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
