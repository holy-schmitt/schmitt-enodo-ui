<template>
  <div>
    <md-card class="card-border">
      <md-card-content>
        <div>
          <div class="header">Operating Expenses</div>
          <md-divider class="divider"></md-divider>
          <ChartPie v-if="loaded" :height="265" :chartData="chartData" :chartOptions="chartOptions"></ChartPie>
        </div>
      </md-card-content>
    </md-card>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator'
import ChartPie from './ChartPie.vue'

@Component({
  components: {
    ChartPie
  }
})
export default class NavBar extends Vue {

  private loaded = false

  private chartData = {
    datasets: [
      {
        data: [20 , 30, 50, 10 , 60, 80],
        backgroundColor: ['#FFA87C', '#D49EFF', '#FF7B70', '#C0C0C0', '#79CCBD', '#F9E79F'] }
      ],
      labels: [
        'Salaries & Personnel',
        'Repairs & Maintenance',
        'Contract Services',
        'Marketing & Advertising',
        'Administrative',
        'Utilities'
      ]
    }
  private chartOptions: object = {
    responsive: true,
    maintainAspectRatio: false
  }

  private mounted() {
    setTimeout(() => {
      this.loaded = true
    }, 500)
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  .card-border {
    border:1px solid #A7BABF;
    box-shadow: none;
    background-color: #FFFFFF;
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
</style>