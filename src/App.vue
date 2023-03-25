<template>
  <h1>{{ title }}</h1>
</template>

<script>
export default {
  data() {
    return {
      title: "Hi world!",
    };
  },
  methods: {
    get() {
      fetch("https://api.adviceslip.com/advice")
        .then((res) => res.json())
        .then((data) => (this.title = data.slip.advice));
    },
  },
  mounted() {
    this.get();
  },
};
</script>

<style scoped></style>
