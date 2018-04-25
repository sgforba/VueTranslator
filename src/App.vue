<template>
  <div id="app" class="text-center">
    <h1>World Translator</h1>
    <h5  class="text-muted">Powered by Vue.js and Yandex</h5>
    <hr>
    <TranslateForm v-on:formSubmit="translateText"></TranslateForm>
    <TranslateOutput v-text="translatedText"></TranslateOutput>
  </div>
</template>

<script>
import TranslateForm from './components/TranslateForm';
import TranslateOutput from './components/TranslateOutput';

export default {
  name: 'App',
  components: {
    TranslateForm,
    TranslateOutput
  },
  data: function(){
    return {
      translatedText: ''
    }
  },
  methods: {
    translateText: function(text, language){
      this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20180425T145120Z.d9d12dddea03a5b4.cae8cf73dccfad278e0e01908b491638dd4c51c2&lang='+language+ '&text='+text)
      .then((response)=> {
        this.translatedText = response.body.text[0];
      })
    }
  }
}
</script>

<style>
body {
  
}
</style>
