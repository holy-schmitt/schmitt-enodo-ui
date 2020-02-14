<template>
  <div>
    <md-card>
      <md-card-header>
        <div class="md-title">
          Operating Expenses
        </div>
      </md-card-header>
      <md-card-content>
        <div>
          <ChartPie v-if="loaded" :height="300" :chartData="chartData" :chartOptions="chartOptions"></ChartPie>
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
</style>