
<template>
  <div class="row" id="translateForm">
    <div id="formWrapper">
      <form id="transForm" class="form-inline well" v-on:submit="formSubmit">
        <input class="form-control" type="text" v-model="textToTranslate" placeholder="Enter a Word...">
        <select class="form-control" v-model="language">
            <option value="es">Spanish</option>
            <option value="zh">Chinese</option>
            <option value="ru">French</option>
            <option value="ru">Arabic</option>
            <option value="ru">Chinese</option>
            <option value="he">Hebrew</option>
            <option value="ru">Russian</option>
        </select>
        <input class="btn btn-primary" type="submit" value="Translate">
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
