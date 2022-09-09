<template>
  <div class="boxed">
    <h2 class="marked-up">{{ msg }}</h2>
  </div>
</template>

<script>
export default {
  name: 'SansHydrate',
  props: {
    msg: { type: String, default: 'I\'m Sans Hydrate' },
  },
  setup (props) {
    console.log('props: ' + JSON.stringify(props))
  }
}
</script>

<style>
  @import './sans-hydrate.css';
</style>