<template>
  <h1>{{ title }}</h1>
  <button @click="get">Новый совет</button>
</template>

<script>
export default {
  data() {
    return {
      title: "",
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
