<template>
  <p>{{ $t('message') }}</p>
</template>

<script>
  import {
    defineComponent
  } from 'vue'

  export default defineComponent({
    name: 'HelloI18n',
    data() {
      return {
        languageArray: ['en', 'hi']
      }
    }
  })
</script>