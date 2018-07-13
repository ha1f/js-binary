<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <binary-view />
  </div>
</template>

<script>
import BinaryView from '@/components/BinaryView'

export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  components: {
    'binary-view': BinaryView
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
</style>
