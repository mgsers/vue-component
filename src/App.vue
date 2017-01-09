<template>
  <div id="app">
    <app-select
    :select-data="source"
    @selectedData='selectedE'>
    </app-select>
    <tag-input
    :ipt-data="source"
    @iptData='iptE'
    >
    </tag-input>
  </div>
</template>

<script>
import appSelect from './components/select'
import tagInput from './components/tagInput'

export default {
  name: 'app',
  components: {
    appSelect,
    tagInput
  },
  data () {
    return {
      source: [{name: 'aa',checked: false,allow: true},
               {name: 'bb',checked: true,allow: true},
               {name: 'cc',checked: false,allow: false},
               {name: 'dd',checked: false,allow: true}]
    }
  },
  methods: {
    selectedE (v) {
      console.log(v);
    },
    iptE (v) {
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
