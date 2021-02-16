<template>
  <div>
    <SearchJokes @search-text="searchText" />
    <Joke
      v-for="joke in jokes"
      :key="joke.id"
      :joke="joke.joke"
      :id="joke.id"
    />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "nuxt-property-decorator";

import Joke from "~/components/Joke.vue";
import SearchJokes from "~/components/SearchJokes.vue";

interface IJoke {
  id: String;
  joke: String;
}

@Component({ components: { Joke, SearchJokes } })
export default class JokesPage extends Vue {
  // Data
  jokes: Array<IJoke> = [];

  // Methods
  async searchText(text: String) {
    const config = {
      headers: {
        Accept: "application/json"
      }
    };

    try {
      const res: any = await this.$axios.get(
        `https://icanhazdadjoke.com/search?term=${text}`,
        config
      );
      this.jokes = res.data.results;
    } catch (err) {
      console.log(err);
    }
  }

  // Lifecycles
  async created() {
    const config = {
      headers: {
        Accept: "application/json"
      }
    };

    try {
      const res: any = await this.$axios.get(
        "https://icanhazdadjoke.com/search",
        config
      );
      this.jokes = res.data.results;
    } catch (err) {
      console.log(err);
    }
  }
}
</script>

<style scoped>
.jokes {
  background-color: beige;
}
</style>
