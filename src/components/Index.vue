<template>
  <div>
    <popup v-model="content">
    </popup>
    <div>弹出框输入的内容是：{{content}}</div>
    <button @click="openPopup">show popup</button>
  </div>
</template>

<script>
import popup from './Popup.vue'
export default {
  components: {
    popup
  },
  data () {
    return {
      content: ''
    }
  },
  methods: {
    openPopup() {
      popup.open()
    }
  }
}
</script>

<style scoped>

</style>
