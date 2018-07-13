<template>
  <div class="table-container">
    <table>
      <tr>
        <th>address</th>
        <th v-for="value in headers" :key="value.id">
          {{ value }}
        </th>
      </tr>
      <tr>
        <td>
          0000
        </td>
        <td v-for="value in values" :key="value.id">{{ value }}</td>
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
      values: [10, 11, 12, 13, 14]
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
