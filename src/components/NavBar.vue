<template>
  <div>
    <md-toolbar class="navbar">
      <img src="../assets/enodo.png" alt="logo" height="42" width="42">
      <md-button class="left-button">
        <img class="toolbar-icon" src="../assets/search.svg" alt="search" height="20" width="20">
        SEARCH
      </md-button>
      <md-button class="left-button">
        <img class="toolbar-icon" src="../assets/tools.svg" alt="tools" height="20" width="20">
        TOOLS
      </md-button>
      <md-button class="left-button">
        <img class="toolbar-icon" src="../assets/properties.svg" alt="properties" height="20" width="20">
        MY PROPERTIES
      </md-button>
      <div class="md-toolbar-section-end">
        <i class="italic">
          Remaining Properties:
        </i>
        <h3 class="remaining-properties">2</h3>
        <img class="toolbar-icon" src="../assets/divider.png" alt="divider" height="5">
        <img class="help" src="../assets/help.svg" alt="help" height="20" width="20">
        <img src="../assets/user.png" alt="user" height="35" width="35">
      </div>
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
  .left-button {
    color: #FFFFFF;
    margin-left: 5vw;
  }
  .toolbar-icon {
    margin-right: 10px;
  }
  .remaining-properties {
    color: #FFFFFF;
    margin-left: 5px;
    margin-right: 15px;
  }
  .italic {
    color: #FFFFFF;
  }
  .help {
    margin-left: 15px;
    margin-right: 20px;
  }
</style>