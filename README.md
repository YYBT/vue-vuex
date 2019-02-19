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
```