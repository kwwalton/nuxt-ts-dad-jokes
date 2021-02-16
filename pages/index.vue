<template>
  <div>Welcome To Dad Jokes</div>
</template>

<script lang="ts">
import { Component, Vue } from "nuxt-property-decorator";

@Component({ components: {} })
export default class HomePage extends Vue {
  head() {
    return {
      title: "Welcome To Dad Jokes",
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
.index {
  background-color: orange;
}
</style>
