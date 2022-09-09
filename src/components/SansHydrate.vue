<template>
  <div :class="styles.boxed">
    <h2 :class="styles.marked">{{ msg }}</h2>
  </div>
</template>

<script>
import { useCssModule } from 'vue'

export default {
  name: 'SansHydrate',
  props: {
    msg: { type: String, default: 'I\'m Sans Hydrate' },
  },
  setup (props) {
    const styles = useCssModule('classes')
    console.log('styles: ' + JSON.stringify(styles))
    console.log('props: ' + JSON.stringify(props))
    return {
      styles
    }
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
.marked {
  color: gold;
}
</style>