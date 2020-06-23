<template>
  <div class="mx-auto bg-info" style="width: 300px; margin:20px">
    <b-card-text style="font-weight: bold; color: white">{{id}}</b-card-text>
    <b-card :title="title" tag="article" style="max-width: 20rem;" class="mb-2">
      <b-card-text>{{body}}</b-card-text>
    </b-card>
  </div>
</template>

<script>
export default {
  name: "card",
  props: {
    id: Number,
    title: String,
    body: String
  }
};
</script>

<style scoped>
id {
  font-weight: bold;
}
</style>