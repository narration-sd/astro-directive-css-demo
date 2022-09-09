<template>
  <div class="dark:bg-gray-500 bg-gray-500 dark:text-amber-200 text-amber-200 p-4 mx-32 my-4 rounded">
   <h2>{{ msg }}</h2>
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