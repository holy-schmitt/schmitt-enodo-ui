<template>
  <div class="top-margin">
    <md-card class="card-border">
      <md-card-content>
        <div class="header">Historical Operating Expenses</div>
        <md-divider class="divider"></md-divider>
        <md-table class="table-offset">
          <md-table-row>
            <md-table-head></md-table-head>
            <md-table-head v-for="header in headers" :key="header">{{header}}</md-table-head> 
          </md-table-row>
          <md-table-row v-for="(row, i) in items" :key="i">
            <md-table-cell>{{row.name}}</md-table-cell>
            <md-table-cell v-for="(value, x) in row.values" :key="x">{{value}}</md-table-cell> 
          </md-table-row>
        </md-table>
      </md-card-content>
    </md-card>
    
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
  .top-margin {
    margin-top: 30px;
  }
  .card-border {
    border:1px solid #A7BABF;
    box-shadow: none;
  }
  .header {
    font-size: .9rem;
    font-weight: bold;
    margin-bottom: 13px;
  }
  .divider {
    margin-bottom: 7px;
    margin-left: -17px;
    margin-right: -17px;
    border:0.5px solid #A7BABF;
  }
  .table-offset {
    padding-right: 30vw;
  }
</style>