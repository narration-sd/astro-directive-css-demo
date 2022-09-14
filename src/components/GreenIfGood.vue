<template>
  <div class="greengood boxed">
    <button v-on:click="makeGreen" class="green-button">Make Green</button>
    <h2 class="greengood">{{ msg }}</h2>
  </div>
</template>

<script>

export default {
  name: 'SansHydrate',
  props: {
    msg: { type: String, default: 'Green would be good...' },
  },
  setup (props) {
    console.log('props: ' + JSON.stringify(props))
    console.log('typeof window: ' + typeof window)

    // except this won't be created on server, will it...
    if (typeof window !== 'undefined') {
      const style = document.createElement("style")
      style.textContent = "greengood { color: yellow; background-color: yellow; }"
      console.log('createdStyle: ' + JSON.stringify(style))
      document.head.appendChild(style)
    }
  },
  created () {
    // also, this will not be created on server
    if (typeof window !== 'undefined') {
      const style = document.createElement("style")
      style.textContent = "greengood { color: yellow; background-color: yellow; }"
      console.log('createdStyle: ' + JSON.stringify(style))
      document.head.appendChild(style)
    }
  },
  methods: {
    makeGreen: function () {
      console.log('making green...')
      if (typeof window !== 'undefined') {
        const style = document.createElement("style")
        console.log('createdStyle:before: ' + JSON.stringify(style))
        style.textContent = ".greengood { color: yellow; background-color: darkgreen; }"
        console.log('createdStyle:after:  ' + style)
        console.log('createdStyle:after:  ' + JSON.stringify(style[0]))
        document.head.appendChild(style)
      }
    }
  }
}
</script>

<style>
.boxed {
  max-width: 200px;
  margin: 20px auto;
  padding: 10px 50px;
  background-color: darkgray;
}
.green-button {
  color: yellow;
  background-color: darkgreen;
}
</style>