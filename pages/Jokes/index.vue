<template>
  <div>
    <SearchJokes v-on:search-text="searchText" />
    <Joke v-for="joke in jokes" :key="joke.id" :id="joke.id" :joke="joke.joke" />
  </div>
</template>

<script>
import axios from "axios";
import Joke from "../../components/Joke"; // not necessary as components are auto imported
import SearchJokes from "../../components/SearchJokes";

export default {
  components: { Joke, SearchJokes }, // again, components are auto imported
  data() {
    return {
      jokes: [],
    };
  },
  async created() {
    const config = {
      headers: {
        Accept: "application/json",
      },
    };

    try {
      const res = await axios.get("https://icanhazdadjoke.com/search", config);

      this.jokes = res.data.results;
    } catch (error) {
      console.log(error);
    }
  },
  methods: {
    async searchText(text) {
      const config = {
        headers: {
          Accept: "application/json",
        },
      };

      try {
        const res = await axios.get(
          `https://icanhazdadjoke.com/search?term=${text}`,
          config
        );

        this.jokes = res.data.results;
      } catch (error) {
        console.log(error);
      }
    },
  },
  head() {
    return {
      title: "Dad Jokes", // This changes the title on the tab
      meta: [
        {
          hid: "description", // unique identifier
          name: "description", // actual meta tag
          content: "Best place for corny dad jokes", // content of the meta tag
        },
      ],
    };
  },
};
</script>

<style>
</style>