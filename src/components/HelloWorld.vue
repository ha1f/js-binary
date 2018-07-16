<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <input @change="selectedFile" name="file" type="file">
    <binary-view :values="values" :step="16" :radix="16" />
  </div>
</template>

<script>
// import BinaryView from '@/components/BinaryView'
import BinaryView2 from '@/components/BinaryView2'

export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      values: []
    }
  },
  components: {
    'binary-view': BinaryView2
  },
  methods: {
    selectedFile: function (event) {
      console.log('start loading')
      event.preventDefault()
      const file = event.target.files[0]
      const reader = new FileReader()
      reader.onload = (e) => {
        console.log('finish loading')
        console.log(e.target.result)
        this.values = new Uint8Array(e.target.result)
      }
      reader.readAsArrayBuffer(file)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
</style>
