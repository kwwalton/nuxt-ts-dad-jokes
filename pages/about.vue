<template>
  <div class="about">
    <h1>About Dad Jokes</h1>
    <p>This is an application that displays corny dad jokes.</p>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "nuxt-property-decorator";

@Component({ components: {} })
export default class AboutPage extends Vue {
  head() {
    return {
      title: "About The App",
      meta: [
        {
          hid: "description",
          name: "description",
          content: "Best place for corny dad jokes."
        }
      ]
    };
  }
}
</script>

<style scoped>
.about {
  background-color: white;
}
</style>
