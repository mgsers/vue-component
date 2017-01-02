<template>
  <div class="select-box" :class="{active: isShow}" @click="selectShow()">aa</div>
</template>

<script>
export default {
  name: 'select',
  data () {
    return {
      isShow: false
    }
  },
  methods: {
    selectShow (){
      if (this.isShow == false) {
        this.isShow = true
      }else {
        this.isShow = false
      }
    }
  }
}
</script>

<style scoped>
.select-box {
  margin: 0 auto;
  width: 150px;
  height: 30px;
  border: 1px solid #ccc;
  cursor: pointer;
  border-radius: 4px;
}
.aa {
  color: red;
}
.select-box.active {
  border: 1px solid #108ee9;
}
.select-box:hover {
  border: 1px solid #108ee9;
}
</style>
