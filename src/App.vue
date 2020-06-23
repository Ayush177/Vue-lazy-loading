<template>
  <div id="app">
    <Header />
    <card v-for="item in items" v-bind="item" v-bind:key="item.id" />
    <observer v-on:intersect="intersected" />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Card from "./components/Card.vue";
import observer from "./components/observer.vue";

export default {
  name: "App",
  components: {
    Header,
    Card,
    observer
  },

  data() {
    return {
      items: [],
      index: 1
    };
  },
  methods: {
    async intersected() {
      const response = await fetch(
        `https://jsonplaceholder.typicode.com/posts?_page=${this.index++}`
      );
      const json = await response.json();
      this.items = [...this.items, ...json];
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
