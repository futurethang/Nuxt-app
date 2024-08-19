<script setup>
import { defineProps } from "vue";

const props = defineProps(["name", "subregion", "flag"]);
</script>

<template>
  <div class="card">
    <div class="labels">
      <h3>{{ name }}</h3>
      <p>{{ subregion }}</p>
    </div>
    <img :src="flag" alt="Flag" />
  </div>
</template>

<style scoped>
div.card {
  display: flex;
  justify-content: space-between;
  align-items: center;
  max-width: 300px;
  padding: 10px;
  border-bottom: 1px solid #f2f2f2;
}

div.labels {
  display: flex;
  flex-direction: column;
}

img {
  height: 50px;
}
</style>
