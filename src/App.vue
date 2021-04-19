<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Salom mening SPA ilovam"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data() {
    return {
      darslar: ['Git', 'Vue', 'Laravel', 'PHP']
    }
  },
  created() {
    this.darslarniOlish()
  },
  methods: {
    darslarniOlish () {
      //
    }
  },
  computed: {
    onlaynStudentlar() {
      return ['Anvar', 'Abror']
    }
  },
  watch: {
    dars() {
      //alert("Yangi dars qo\'shildi");
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
