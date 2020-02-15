<template>
  <div class="top-margin">
    <md-card class="card-border">
      <md-card-content>
        <div class="header">Historical Operating Expenses</div>
        <md-divider class="divider"></md-divider>
        <md-table class="table-offset">
          <md-table-row>
            <md-table-head class="table-row-border text"></md-table-head>
            <md-table-head class="table-row-border text" v-for="header in headers" :key="header">{{header}}</md-table-head> 
          </md-table-row>
          <md-table-row v-for="(row, i) in items" :key="i">
              <md-table-cell :class="row.isTotal ? 'bold-italics' : 'table-row-border'">{{row.name}}</md-table-cell>
              <md-table-cell :class="row.isTotal ? 'bold-italics text' : 'table-row-border text'" v-for="(value, x) in row.values" :key="x">{{formatDollar(value)}}</md-table-cell> 
          </md-table-row>
        </md-table>
      </md-card-content>
    </md-card>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator'

@Component({
  methods: {
      formatDollar(data) {
        if (data) {
          return '$' + data.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ',');
        } else {
          if (data === '0') {
            return '$0';
          } else { return ''; }
        }
      }
    }
})
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
    background-color: #FFFFFF;
    margin-bottom: 40px;
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
    padding-right: 20vw;
  }
  .table-row-border {
    border-bottom: 0.5px solid #C9D3D6;
  }
  .bold-italics {
    font-weight: bold;
    font-style: italic;
    border-bottom: 0.5px solid #C9D3D6;
  }
  .text {
    text-align: right;
  }
</style>