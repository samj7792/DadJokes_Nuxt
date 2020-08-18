<template>
  <div>Jokes</div>
</template>

<script>
export default {
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