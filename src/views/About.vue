<template>
  <div class="about">
    <h1>这个数字是：{{count}}</h1>
    <p>
      <button @click="hander">增加</button>
    </p>
  </div>
</template>
<!-- script setup模式 -->
<script setup>
import {computed} from 'vue'
import {useCounterStore} from '../store/index'

    const useState = useCounterStore()
    const hander = ()=>{
      useState.increment()
    }
    const count=computed(()=>useState.count)

</script>

<!-- setup hooks 模式 -->
<!-- <script>
import {computed} from 'vue'
import {useCounterStore} from '../store/index'
export default {
  setup() {
    const useState = useCounterStore()
    const hander = ()=>{
      useState.increment()
    }
    return{
      count:computed(()=>useState.count),
      hander
    }
  },
}
</script> -->