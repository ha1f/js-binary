<template>
  <div class="table-container">
    <table>
      <tr>
        <th>address</th>
        <th v-for="header in headers" :key="header.id">
          {{ header }}
        </th>
      </tr>
      <tr v-for="i in Math.ceil(values.length / 10)" :key="i">
        <td>
          0000
        </td>
        <th v-for="header in headers" :key="header.id">
          {{ values[(i - 1) * 10 + header] }}
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
      headers: Array.from(Array(10).keys()),
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
