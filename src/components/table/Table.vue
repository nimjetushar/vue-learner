<template>
  <table id='table-component'>
    <thead>
      <tr>
        <th v-for='(col, index) in columns' :key="index">
          {{ col.name }}
        </th>
      </tr>
    </thead>
    <tbody>
      <tr v-for='(item, index) in data' :key="index">
        <td v-for='(col, idx) in columns' :key="idx">{{item[col.field]}}</td>
      </tr>
    </tbody>
  </table>
</template>

<script>
export default {
  template: '#table-component',
  name: 'Table',
  props: {
    data: {
      type: Array,
      required: true
    },
    columns: {
      type: Array,
      required: true
    }
  }
}
</script>

<style lang="sass" scoped>
  @import './table.style.scss'
</style>
