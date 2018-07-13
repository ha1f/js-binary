<template>
  <div class="table-container">
    <table>
      <tr>
        <th>address</th>
        <th v-for="j in 10" :key="j">
          +{{ j - 1 }}
        </th>
      </tr>
      <tr v-for="i in Math.ceil(values.length / 10)" :key="i">
        <td>
          {{ (i - 1) * 10 }}
        </td>
        <th v-for="j in 10" :key="j">
          {{ values[(i - 1) * 10 + j - 1] }}
        </th>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  name: 'BinaryView',
  data () {
    return {
      values: [10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.table-container table {
  margin: auto;
}
</style>
