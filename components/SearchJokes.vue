<template>
  <div>
    <form @submit.prevent="onSubmit">
      <input type="text" v-model="text" placeholder="Search Jokes" />
      <input type="submit" value="Search Jokes" />
    </form>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "nuxt-property-decorator";

@Component
export default class SearchJokes extends Vue {
  // Data
  text = "";

  // Methods
  onSubmit() {
    this.$emit("search-text", this.text);
    this.text = "";
  }
}
</script>
