<template>
  <div>
    <h2>Welcome to the best corny dad jokes app on the web</h2>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: "Welcome to Dad Jokes", // This changes the title on the tab
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
