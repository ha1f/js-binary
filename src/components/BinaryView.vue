<template>
  <div class="table-container">
    <table>
      <tr>
        <th>address</th>
        <th v-for="j in step" :key="j">
          +{{ (j - 1).toString(radix) }}
        </th>
      </tr>
      <tr v-for="i in Math.ceil(values.length / step)" :key="i">
        <td>
          {{ ((i - 1) * step).toString(radix) }}
        </td>
        <td-if-present v-for="j in step" :key="j" v-bind:value="values[(i - 1) * step + j - 1]" v-bind:radix="radix"></td-if-present>
      </tr>
    </table>
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
  name: 'BinaryView',
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
.table-container table {
  margin: auto;
}
</style>
