<template>
  <nuxt-link :to="linkDestination">
    <div class="joke">
      <p>{{ joke }}</p>
    </div>
  </nuxt-link>
</template>

<script lang="ts">
import { Component, Prop, Vue } from "nuxt-property-decorator";

@Component
export default class Joke extends Vue {
  @Prop(String) readonly joke!: string;
  @Prop(String) readonly id!: string;

  // Computed
  get linkDestination() {
    return `jokes/${this.id}`;
  }
}
</script>

<style scoped>
.joke {
  padding: 1rem;
  border: 1px dotted purple;
  margin-bottom: 1rem;
}
</style>
