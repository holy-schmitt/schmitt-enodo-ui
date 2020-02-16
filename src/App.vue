<template>
  <div id="app">
    <NavBar :menuItems="menuItems"/>
    <SecondNavBar :property="property"/>
    <div class="container">
      <div class="md-layout">
        <div class="md-layout-item md-size-20">
          <PropertySummary :property="property"/>
        </div>
        <div class="md-layout-item md-layout">
          <div class="md-layout-item">
            <GPRCard/>
          </div>
          <div class="md-layout-item">
            <OperatingExpensesCard/>
          </div>
          <div class="md-layout-item md-size-100">
            <HistoricalOperatingExpenses :headers="opexHeaders" :items="opexItems"/>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'
import NavBar from './components/NavBar.vue'
import SecondNavBar from './components/SecondNavBar.vue'
import PropertySummary from './components/PropertySummary.vue'
import HistoricalOperatingExpenses from './components/HistoricalOperatingExpenses.vue'
import GPRCard from './components/GPRCard.vue'
import OperatingExpensesCard from './components/OperatingExpensesCard.vue'
@Component({
  components: {
    NavBar,
    PropertySummary,
    HistoricalOperatingExpenses,
    SecondNavBar,
    GPRCard,
    OperatingExpensesCard
  },
})
export default class App extends Vue {

  private menuItems: object[] = [
    { name: 'Property Analysis', active: true },
    { name: 'Rent Roll Analyzer', active: false },
    { name: 'Operating Statement Parser', active: false },
    { name: 'Markert Analysis', active: false }
  ]

  private property: object = {
    name: 'West Loop Luxury',
    address: '320 N Canal St, Chicago, IL 60606',
    yearBuild: '2010',
    numberUnits: '240',
    propetyType: 'Garden',
    avm: 7403292
  }

  private opexHeaders = ['T12', 'T9', 'T6', 'T3']
  private opexItems = [
    {
      name: 'Gross Potential Revenue',
      values: [8267438, 8256651, 8254872, 8293104],
      isTotal: false,
    },
    {
      name: 'Vacancy Loss',
      values: [-1914476, -1280007, -781996, -592272],
      isTotal: false,
    },
    {
      name: 'Collection Loss',
      values: [-8589, -11452, -17178, 0],
      isTotal: false,
    },
    {
      name: 'Concessions',
      values: [-414478, -383775, -278352, -43556],
      isTotal: false,
    },
    {
      name: 'Net Rentable Income',
      values: [5929895, 6581417, 7177346, 7657276],
      isTotal: true,
    },
    {
      name: 'Other Income',
      values: [358980, 408028, 489346, 476672],
      isTotal: false,
    },
    {
      name: 'Administrative',
      values: [0, 0, 0, 0],
      isTotal: false,
    },
    {
      name: 'EGI',
      values: [6288875, 6989445, 7666692, 8133948],
      isTotal: true,
      notItalic: true,
    },
    {
      name: null,
      values: ['-', '-', '-', '-'],
      isTotal: false,
    },
    {
      name: 'Property Taxes',
      values: [1099828, 1053756, 1179530, 1165516],
      isTotal: false,
    },
    {
      name: 'Insurance',
      values: [357246, 442201, 595266, 293508],
      isTotal: false,
    },
    {
      name: 'Contract Services',
      values: [326058, 377784, 570950, 582436],
      isTotal: false,
    },
    {
      name: 'Repairs & Maintenance',
      values: [380047, 498688, 589116, 498792],
      isTotal: false,
    },
    {
      name: 'Utilities',
      values: [405150, 412069, 406714, 554088],
      isTotal: false,
    },
    {
      name: 'Water & Sewage',
      values: [0, 0, 0, 0],
      isTotal: false,
    },
    {
      name: 'Management Fees',
      values: [122424, 135312, 147842, 156456],
      isTotal: false,
    },
    {
      name: 'Salaries & Personnel',
      values: [453897, 447720, 439506, 395428],
      isTotal: false,
    },
    {
      name: 'Marketing & Advertising',
      values: [204256, 187792, 136698, 123156],
      isTotal: false,
    },
    {
      name: 'Total Expenses',
      values: [3348906, 3555322, 4065622, 3769380],
      isTotal: true,
    },
    {
      name: 'Reserves',
      values: [0, 0, 0, 0],
      isTotal: false,
    },
    {
      name: 'Total Expenses & Reserves',
      values: [3348906, 3555322, 4065622, 3769380],
      isTotal: true,
    },
    {
      name: null,
      values: ['-', '-', '-', '-'],
      isTotal: false,
    },
    {
      name: 'Net Cash Flow',
      values: [2939969, 3434123, 3601070, 4364568],
      isTotal: true,
    }
  ]
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
.container {
  padding-top: 4vh;
  padding-left: 5vw;
  padding-right: 5vw;
  background-color: #FBFBFB;
}
</style>
