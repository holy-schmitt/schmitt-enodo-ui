<template>
  <!-- <div>
    <div>
      <a v-for="item in menuItems" :key="item.name" :class="item.active ? 'active' : ''">{{item.name}}</a>
    </div>
    <div>
      <a>Go To Platform</a>
    </div>
    <div>
      <a>{{userInitials}}</a>
    </div>
  </div> -->
  <div>
    <md-toolbar class="navbar">
      <!-- <h3 class="header" style="flex: 1">Title</h3> -->
      <img src="../assets/enodo.png" alt="logo" height="42" width="42">
      <md-button class="button">
        <img class="toolbar-icon" src="../assets/search.svg" alt="search" height="20" width="20">
        SEARCH
      </md-button>
      <md-button class="button">
        <img class="toolbar-icon" src="../assets/tools.svg" alt="search" height="20" width="20">
        TOOLS
      </md-button>
      <md-button class="button">
        <img class="toolbar-icon" src="../assets/properties.svg" alt="search" height="20" width="20">
        MY PROPERTIES
      </md-button>
    </md-toolbar>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator'

@Component
export default class NavBar extends Vue {
    @Prop()
    private userInitials!: string

    @Prop()
    private menuItems!: object[]
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  .navbar { 
    background-color: #374950;
  }
  .button {
    color: #FFFFFF;
    margin-left: 5vw;
  }
  .toolbar-icon {
    margin-right: 10px;
  }
</style>