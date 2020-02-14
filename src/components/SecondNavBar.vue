<template>
  <div>
    <md-toolbar>
      <h3>Property Analysis</h3>
      <div class="property">
        <u>{{property.name ? property.name : property.address}}</u>
      </div>
      <div class="md-toolbar-section-end">
        <md-button class="button-outline">Share</md-button>
        <md-button class="button-fill">Export</md-button>
      </div>
    </md-toolbar>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator'

@Component
export default class SecondNavBar extends Vue {
    @Prop()
    private property!: object
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  .property {
    margin-left: 20px;
    font-size: 1.4rem;
    color: #9D9D9D;
  }
  .button-fill {
    background-color: #88B144;
    color: #FFFFFF;
    text-transform: capitalize;
  }
  .button-outline {
    color: #88B144;
    border:2px solid #88B144;
    text-transform: capitalize;
  }
</style>