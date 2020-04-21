<template>
  <button @click="increment">Count is: {{ state.count }}</button>
  The doubled count is: {{ state.double }}
</template>

<script>
import {reactive, computed} from 'vue'

export default {
  setup() {
    const state = reactive({
      count: 0,
      double: computed(() => state.count * 2),
    })

    const increment = () => state.count++

    return {
      state,
      increment,
    }
  },
}
</script>
