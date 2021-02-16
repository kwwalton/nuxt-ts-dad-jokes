<template>
  <div class="joke-page">
    <nuxt-link to="/jokes">Back To Jokes</nuxt-link>
    <p>{{ joke }}</p>
    <hr />
    <small>Joke ID: {{ $route.params.id }}</small>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "nuxt-property-decorator";

interface IJoke {
  id: String;
  joke: String;
  status?: Number;
}

@Component
export default class JokePage extends Vue {
  // Data
  joke = {} as IJoke;

  // Lifecycles
  async created() {
    const config = {
      headers: {
        Accept: "application/json"
      }
    };

    try {
      const res: any = await this.$axios.get(
        `https://icanhazdadjoke.com/j/${this.$route.params.id}`,
        config
      );
      this.joke = res.data.joke;
    } catch (err) {
      console.log(err);
    }
  }
}
</script>
