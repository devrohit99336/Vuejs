<template>
  <p>{{ $t('message') }}</p>
  <div class="lang-dropdown">
    <select v-model="$i18n.locale" @change="switchLang()">
      <option v-for="(lang, i) in languageArray" :key="`lang${i}`" :value="lang">
        <p v-if="lang == 'en'">English</p>
        <p v-else>हिन्दी</p>
      </option>
    </select>
  </div>
  <!-- v-model="$i18n.locale" -->
</template>

<script>
  // import { defineComponent } from 'vue'

  export default ({
    name: 'langSwitcher',
    mounted() {
      let language = localStorage.getItem("selectLang");
      if (language == null) {
        localStorage.setItem('selectLang', 'en');
      }
      this.$i18n.locale = localStorage.getItem("selectLang");
      console.log('getetd value:' + this.$i18n.locale)
    },
    data() {
      return {
        languageArray: ['en', 'hi'],
      }
    },
    methods: {
      switchLang() {
        console.log("welcome to swicther :" + this.$i18n.locale);
        localStorage.setItem('selectLang', this.$i18n.locale);
      }
    }
  })
</script>