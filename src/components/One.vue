<template>
  <footer>
    <p>我是组件一</p>
    <p>{{propsmsg}}</p>
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
  props: [
    'propsmsg'
  ],
  mounted () {

  },
  methods: {
    emitEvent () {
      this.$emit('my-event', 'emit 来自组件一的消息')
      this.$store.commit('increment', 'vuex 来自组件一的消息')
    }
  },
  computed: {
    listenstage () {
      return this.$store.state.msg
    }
  },
  watch: {
    listenstage () {
      console.log('ddd' + this.$store.state.msg)
      this.msg1 = this.$store.state.msg
    }
  }

}
</script>

<style scoped>
footer {
  background: #FF0000;
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
