<template lang="html">

<div class="translaterform  notification">
  <div class="container">
  <div class="columns">
    <div class="column ">
      <form  v-on:submit="post">
        <div class="field is-grouped is-grouped-centered">
          <p class='control '>
            <input class='input is-primary' type="text" v-model="wordtranslate">
            </p>
            <p class='control '>
              <span class='select'>
              <select  name="language"  v-model='language'>
                <option value="hi">Hindi</option>
                <option value="ru">Russia</option>
                <option value="gu">Gujarati</option>
                <option value="es">Spanish</option>
              </select>
              </span>
            </p>
            <p class='control'>
              <input type="submit"  class="button is-primary is-outlined" value="translate">

          </p>
        </div>
      </form>
  </div>
  </div>
</div>
</div>
</template>

<script>
export default {
  name:'translaterform',
  data(){
    return{
      //word to translate
      wordtranslate:'',
      //language to translate
      language:''
    }
  },
  methods:{
    post:function(e){
      //passing the word and language to the parent components so that it can access their.
      this.$emit('WTtranslate',this.wordtranslate,this.language);
      e.preventDefault();
    }
  }
}
</script>

<style lang="css">
</style>
