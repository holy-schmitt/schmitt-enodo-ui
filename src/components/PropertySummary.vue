<template>
  <div>
    <md-card class="card-border">
      <md-card-media>
        <img src="https://maps.googleapis.com/maps/api/streetview?size=400x200&pitch=10&fov=180&location=320%20N%20Canal%20St,%20Chicago,%20IL%2060606&key=AIzaSyApsGVNO-Ms2sIJM4PtmwC5VfeutsZSExo">
      </md-card-media>
      <md-card-content>
        <div class="street-header">{{property.address.split(",")[0]}}</div>
        <div class="street-subheader">{{property.address.split(",")[1]+property.address.split(",")[2]}}</div>
        <div class="description">
          {{property.numberUnits ? property.numberUnits : '--'}} /
          {{property.propetyType ? property.propetyType : '--'}} /
          {{property.yearBuild ? property.yearBuild : '--'}}
        </div>
        <div class="avm">
          {{formatAVM(property.avm)}}
        </div>
        <LateralNav :options="propertySections" />
      </md-card-content>
    </md-card>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator'
import LateralNav from './LateralNav.vue'

@Component({
  components: {
    LateralNav
  },
  methods: {
      formatAVM(avm) {
        if (avm) {
          return '$' + avm.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ',') + ' AVM';
        } else {
          return '--';
        }
      }
    }
})
export default class NavBar extends Vue {
    @Prop()
    private property!: object

    private propertySections: object[] = [
        {name: 'Comparables', icon: require('@/assets/comparables.png'), selected: false},
        {name: 'Operating Expenses', icon: require('@/assets/operating.svg'), selected: false},
        {name: 'Rent roll / Unit Mix', icon: require('@/assets/grid.png'), selected: true},
        {name: 'Amenities', icon: require('@/assets/amenities.png'), selected: false},
        {name: 'Market', icon: require('@/assets/market.png'), selected: false}
    ]
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  .street-header {
    font-size: 1.4rem;
    font-weight: bold;
    margin-bottom: 7px;
    margin-top: 5px;
  }
  .street-subheader {
    font-size: 1.1rem;
    font-weight: lighter;
  }
  .description {
    font-size: 1.3rem;
    margin-top: 13px;
    margin-bottom: 20px;
  }
  .avm {
    font-size: 1.3rem;
    font-weight: bold;
    color: #88B144;
    margin-bottom: 5px;
  }
  .card-border {
    border:1px solid #A7BABF;
    box-shadow: none;
    background-color: #FFFFFF;
    margin-right: 20px;
  }
</style>