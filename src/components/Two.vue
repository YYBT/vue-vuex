<template>
  <footer>
    <p>我是组件二</p>
    <button @click="emitEvent">点我发消息</button>
      <h1 class="msg1">{{ msg1 }}</h1>
  </footer>
</template>

<script>
export default {
  data () {
    return {
      msg1: 'vuex'
    }
  },
  methods: {
    getMyEvent (msg) {
      this.copyright = '我是组件二' + msg // 接收的数据--------->我是子组件中的数据
    },
    emitEvent () {
      this.$emit('my-event2', 'emit 来自组件二的消息')
      this.$store.commit('increment', 'vuex 来自组件二的消息')
    }
  },
  computed: {
    listenstage () {
      return this.$store.state.msg
    }
  },
  watch: {
    listenstage () {
      this.msg1 = this.$store.state.msg
    }
  }
}
</script>

<style scoped>
footer {
  background: #666;
  padding: 6px;
}
footer p {
  color: pink;
  text-align: center;
}
.msg1 {
  background: #ff0000
}
</style>
