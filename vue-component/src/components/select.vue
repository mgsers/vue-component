<template>
  <div>
    <div class="select-box"
      :class="{active: isShow}"
      @click="selectShow()">
      <span>
        {{ selectName }}
      </span>
    </div>
    <ul class="select-ul" v-if="isShow">
      <li  v-for="item in selectData" @click="liSelect(item)">{{ item }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'select',
  props: {
    selectData: {
      type: Array,
      required: true
    }
  },
  data () {
    return {
      isShow: false,
      selectName: '请选择'
    }
  },
  methods: {
    selectShow (){
      if (this.isShow == false) {
        this.isShow = true
      }else {
        this.isShow = false
      }
    },
    liSelect (num) {
      this.selectName = num
      this.isShow = false;
      this.$emit('selectedData',num)
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
.select-ul {
  margin: 0;
  list-style-type: none;
  margin: 0 auto;
  padding: 0;
  width: 150px;
  box-shadow: 0 5px 30px #e4ebf1;
}
.select-ul li {
  height: 30px;
  cursor: pointer;
}
.select-ul li:hover {
  background-color: #f7f7f7;
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
