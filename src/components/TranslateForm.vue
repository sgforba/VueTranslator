
<template>
  <div class="row" id="translateForm">
    <div id="formWrapper">
      <form id="transForm" class="form-inline well" v-on:submit="formSubmit">
        <input class="form-control" type="text" v-model="textToTranslate" placeholder="Enter a Word...">
        <select class="form-control" v-model="language">
            <option value="es">Spanish</option>
            <option value="zh">Chinese</option>
            <option value="fr">French</option>
            <option value="ar">Arabic</option>
            <option value="hi">Hindi</option>
            <option value="de">German</option>
            <option value="he">Hebrew</option>
            <option value="ru">Russian</option>
            <option value="pt">Portuguese</option>
            <option value="bn">Bengali</option>
            <option value="ja">Japanese</option>
            <option value="pa">Punjabi</option>
        </select>
        <input class="btn btn-primary" type="submit" value="Run Translation">
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: 'translateForm',
  data() {
      return {
          textToTranslate: ''
      }
  },
  created() {
      this.language = 'es';
  },
  methods: {
      formSubmit(e){
          this.$emit('formSubmit', this.textToTranslate, this.language)      
          e.preventDefault();
      }
  }
}
</script>

<style>
    #transForm {
        background: #efefef;
        border-radius: 12px;
        border: 1px soli #ccc;
        padding: 20px;
    }
    .form-control {
        margin-right: 10px;
    }
    #formWrapper {
        margin: 0 auto;
    }
</style>
