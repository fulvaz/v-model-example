<template lang="html">
  <div class="container" v-show="show">
     <div class="popup"> 
      <span class="title">请输入验证信息</span>
      <input type="text" class="input" v-model="inputText">
      <button class="send-btn btn" @click="onSubmit">提交</button>
      <button class="close-btn btn" @click="onCancel">取消</button>
     </div> 
  </div>
</template>

<script>
let that
export default {
  props: {
    value: String
  },
  data () {
    return {
      show: false,
      inputText: ''
    }
  },
  created () {
    that = this // 给全局函数使用
  },
  methods: {
    onSubmit() {
      this.$emit('input', this.inputText)
      this.show = false
    },
    onCancel() {
      // do sth when cancel
      this.$emit('cancel', this.inputText)
      this.show = false
    }
  },
  open () {
    that.show = true
  },
  close () {
    that.show = false
  }
}
</script>


<style lang="scss" scoped>
  .container {
    position: fixed;
    top: 0;
    left: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100vw;
    height: 100vh;
    background: rgba(0, 0, 0, 0.8);

  }

  .popup {
    width: 50vw;
    text-align: center;
    background: #FFF;
    padding: 1.25rem;

    .input {
      margin: 0 auto;
    }
    
    & > .input,.title {
      display: block;
    }
  }

</style>
