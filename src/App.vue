<template>
  <div id="app">
    <div>
      <h3>Langs:
        <a
          v-for="lang in langs"
          :key="lang"
          href
          @click.prevent="changeLanguage(lang)"
        >{{ lang.toUpperCase() }} | </a>
      </h3>
    </div>
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <router-view/>
  </div>
</template>

<script>
  export default {
    name: 'App',

    data() {
      return {
        langs: ['en', 'ru']
      }
    },

    methods: {
      changeLanguage(lang) {
        this.$i18n.locale = lang;
      }
    }
  }
</script>
