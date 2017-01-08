<template>
  <div id="app">
    <app-select
    :select-data="source"
    @selectedData='selectedE'>
  </app-select>
  </div>
</template>

<script>
import appSelect from './components/select'

export default {
  name: 'app',
  components: {
    appSelect
  },
  data () {
    return {
      source: ['ww','ee','rr','tt']
    }
  },
  methods: {
    selectedE (v) {
      console.log(v);
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
