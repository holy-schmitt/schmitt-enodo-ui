<template>
  <div>
    <md-toolbar>
      <h3 style="flex: 1">Property Analysis</h3>
      <div>
        {{property.name ? property.name : property.address}}
      </div>
      <md-button class="md-raised md-primary">Share</md-button>
      <md-button class="md-raised md-primary">Export</md-button>
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
</style>