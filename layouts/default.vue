<template>
  <div class="something">
    <div class="container">
      <AppHeader />
      <nuxt />
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "nuxt-property-decorator";
import AppHeader from "~/components/AppHeader.vue";

@Component({ components: { AppHeader } })
export default class DefaultLayout extends Vue {}
</script>

<style lang="scss" scoped>
.something {
  background-color: pink;

  .container {
    max-width: 800px;
    margin: 2rem;
    overflow: hidden;
    padding: 1rem 2rem;
    background-color: white;
  }
}
</style>
