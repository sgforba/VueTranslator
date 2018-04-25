<template>
  <h3 id="translateText" class="text-success">
      {{translatedText}}
  </h3>
</template>

<script>
export default {
  name: 'translateOutput',
  props: ['translatedText']

}
</script>

<style>
    #translateText {
        margin-top: 30px;
    }
</style>
