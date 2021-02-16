<template>
  <header class="header">
    <nuxt-link to="/"><h1 class="title">Dad Jokes</h1></nuxt-link>
    <ul>
      <li><nuxt-link to="/">Home</nuxt-link></li>
      <li><nuxt-link to="/jokes">Jokes</nuxt-link></li>
      <li><nuxt-link to="/about">About</nuxt-link></li>
    </ul>
  </header>
</template>

<script lang="ts">
import { Component, Vue } from "nuxt-property-decorator";

@Component({ components: {} })
export default class AppHeader extends Vue {}
</script>

<style lang="scss" scoped>
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 1rem;
  padding-bottom: 1rem;
  border-bottom: 1px dotted #ccc;

  h1 {
    font-size: 3rem;
    color: purple;
  }

  ul {
    display: flex;
    list-style: none;
  }

  a {
    display: inline-flex;
    background-color: blue;
    color: white;
    padding: 0.3rem 1rem;
    margin-right: 0.5rem;
  }
}
</style>
