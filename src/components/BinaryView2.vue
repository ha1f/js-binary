<template>
  <div class="container">
    <span tr v-for="(value, index) in values" :key="index">
      {{ value }}
      <br v-if="index % 10 === 9">
    </span>
  </div>
</template>

<script>
import Vue from 'vue'

const TdIfPresent = Vue.extend({
  data () {
    return {}
  },
  props: [ 'value', 'radix' ],
  // hide if value is undefined
  template: '<td v-show="value != null">{{ (value || 0).toString(radix || 10) }}</td>'
})

export default {
  name: 'BinaryView2',
  data () {
    return {}
  },
  props: ['step', 'radix', 'values'],
  components: {
    'td-if-present': TdIfPresent
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container {
  width: 549px;
  margin: auto;
}
span {
  display: inline-block;
  width: 50px;
}
</style>
