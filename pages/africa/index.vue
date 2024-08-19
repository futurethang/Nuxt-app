<script setup>
import { ref, onMounted } from "vue";
import Card from "@/components/Card.vue";

const countries = ref([]);

onMounted(async () => {
  const response = await fetch("https://restcountries.com/v3.1/region/Africa");
  countries.value = await response.json();
});
</script>

<template>
  <div>
    <h1>Africa Page</h1>
    <p>Welcome to the Africa page!</p>
    <ul>
      <li v-for="country in countries" :key="country.cca3">
        <Card
          :name="country.name.common"
          :subregion="country.subregion"
          :flag="country.flags.png"
        />
      </li>
    </ul>
  </div>
</template>

<style scoped>
ul {
  list-style-type: none;
  padding: 0;
}
</style>
