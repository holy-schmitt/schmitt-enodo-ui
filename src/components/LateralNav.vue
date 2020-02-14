<template>
  <div>
    <div v-for="(value, x) in options" :key="x" :class="value.selected ? 'selected' : ''">
      {{value.name}}
    </div>
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
</style>