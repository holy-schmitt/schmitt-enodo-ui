<template>
  <div>
    <md-list>
      <div v-for="(value, x) in options" :key="x" :class="value.selected ? 'selected' : ''">
        <div v-if="value.selected">
          <md-list-item class="selected-item">
            <img class="selected-icon" :src=value.icon alt="selected" height="20px" width="20px">
            <span class="md-list-item-text"><b>{{value.name}}</b></span>
          </md-list-item>      
        </div>
        <div v-else>
          <md-list-item>
            <img class="icon" :src=value.icon alt="icon" height="25px" width="25px">
            <span class="md-list-item-text"><b>{{value.name}}</b></span>
          </md-list-item>    
        </div>
      </div>
    </md-list>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator'

@Component
export default class NavBar extends Vue {
    @Prop()
    private options!: object[]
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  .icon {
    margin-right: 15px;
    margin-left: -15px;
  }
  .selected-icon {
    margin-right: 16px;
    margin-left: 4px;
  }
  .selected-item {
    background-color: #374950;
    color: #FFFFFF;
    margin-left: -16px;
    margin-right: -16px;
  }
</style>