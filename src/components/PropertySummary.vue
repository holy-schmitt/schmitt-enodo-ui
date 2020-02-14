<template>
  <div>
    <div class="image">
      <img src="https://maps.googleapis.com/maps/api/streetview?size=400x200&pitch=10&fov=180&location=320%20N%20Canal%20St,%20Chicago,%20IL%2060606&key=AIzaSyApsGVNO-Ms2sIJM4PtmwC5VfeutsZSExo">
        <!-- Name: {{property.name}} -->
        Street Address: {{property.address}}  
        # Units: {{property.numberUnits ? property.numberUnits : '--'}}
        Type: {{property.propetyType ? property.propetyType : '--'}}
        Year Build: {{property.yearBuild ? property.yearBuild : '--'}}
        AVM: {{property.avm ? property.avm : '--'}}
    </div>
    <LateralNav :options="propertySections" />
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator'
import LateralNav from './LateralNav.vue'


@Component({
  components: {
    LateralNav
  }
})
export default class NavBar extends Vue {
    @Prop()
    private property!: object

    private propertySections: object[] = [
        {name: 'Comparables', selected: false},
        {name: 'Operating Expenses', selected: true},
        {name: 'Rent roll / Unit Mix', selected: false},
        {name: 'Amenities', selected: false},
        {name: 'Market', selected: false}
    ]
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
</style>