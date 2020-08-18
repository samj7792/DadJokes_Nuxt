<template>
  <div>
    <h1>About DadJokes</h1>
    <p>This is an app that displays dad jokes</p>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: "About The App", // This changes the title on the tab
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