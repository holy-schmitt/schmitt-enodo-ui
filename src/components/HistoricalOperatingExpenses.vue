<template>
  <div>
    <table>
      <tr>
        <th></th>
        <th v-for="header in headers" :key="header">{{header}}</th> 
      </tr>
      <tr v-for="(row, i) in items" :key="i">
        <td>{{row.name}}</td>
        <td v-for="(value, x) in row.values" :key="x">{{value}}</td> 
      </tr>
    </table>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator'

@Component
export default class NavBar extends Vue {
    @Prop()
    private headers!: string[]

    @Prop()
    private items!: object[]

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
</style>