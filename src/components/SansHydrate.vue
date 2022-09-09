<template>
  <div class="boxed">
    <h2 class="marked-up">{{ msg }}</h2>
  </div>
</template>

<script setup>
import { useCssModule } from 'vue'
</script>

<script>
export default {
  name: 'SansHydrate',
  props: {
    msg: { type: String, default: 'I\'m Sans Hydrate' },
  },
  setup (props) {
    useCssModule('classes')
    console.log('props: ' + JSON.stringify(props))
  }
}
</script>

<style module="classes">
.boxed {
  max-width: 200px;
  margin: 20px auto;
  padding: 10px 50px;
  background-color: darkgray;
}
.marked-up {
  color: gold;
}
</style>