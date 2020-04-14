<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <label for="locale">locale</label>
    <select v-model="locale">
      <option>en</option>
      <option>ja</option>
      <option>简体中文</option>
    </select>
    <p>message: {{ $t('hello') }}</p>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data () { return { locale: 'en' } },
  watch: {
    locale (val) {
      if (val == '简体中文') {
        val = 'zh-CN'
      }
      this.$i18n.locale = val
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

<i18n src="@yaml/ja.yml"></i18n>
<i18n src="@yaml/zh-CN.yml"></i18n>
<i18n src="@yaml/en.yml"></i18n>
