# 学习

``` bash
import Vuex from 'vuex'

Vue.use(Vuex)

const store = new Vuex.Store({
  state: {
    msg: 'vuex 原始数据'
  },
  mutations: {
    increment (state, msg) {
      state.msg = msg
    }
  }
})

this.$emit('my-event', 'emit 来自组件一的消息')
this.$store.commit('increment', 'vuex 来自组件一的消息')

```