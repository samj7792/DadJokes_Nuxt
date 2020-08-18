<template>
  <div>Jokes</div>
</template>

<script>
import axios from "axios";

export default {
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