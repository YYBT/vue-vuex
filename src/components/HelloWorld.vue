<template>
  <div class="hello">
    <div style="background: #42b983;margin-bottom: 20px;">
      <h1>{{ emitMsg }}</h1>
      <h1 class="msg1">{{ vuexMsg }}</h1>
      <button @click="propsEvent">点我发消息</button>
    </div>
    <app-one @my-event="getMyEvent" :propsmsg='propsmsg'  style="margin-bottom: 20px;"></app-one>
    <app-two @my-event2="getMyEvent2"></app-two>
  </div>
</template>

<script>
import One from './One'
import Two from './Two'

export default {
  name: 'HelloWorld',
  components: {
    'app-one': One,
    'app-two': Two
  },
  data () {
    return {
      emitMsg: 'Welcome to Your Vue.js App',
      vuexMsg: this.$store.state.msg,
      propsmsg: 'propsmsg'
    }
  },
  methods: {
    propsEvent () {
      this.propsmsg = '我改变了 props'
    },
    getMyEvent (msg) {
      this.emitMsg = msg // 接收的数据--------->我是子组件中的数据
    },
    getMyEvent2 (msg) {
      this.emitMsg = msg // 接收的数据--------->我是子组件中的数据
    }
  },
  computed: {
    listenstage () {
      return this.$store.state.msg
    }
  },
  watch: {
    listenstage () {
      this.vuexMsg = this.$store.state.msg
    }
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.msg1 {
  background: #ff0000
}
</style>
