<script setup>
import { ref, onMounted } from "vue";
import Card from "@/components/Card.vue";

const countries = ref([]);

onMounted(async () => {
  try {
    const response = await fetch(
      "https://restcountries.com/v3.1/region/America"
    );
    countries.value = await response.json();
    console.log(countries.value);
  } catch (error) {
    console.error(error);
  }
});
</script>

<template>
  <ul>
    <li v-for="country in countries" :key="country.cca3">
      <Card
        :name="country.name.common"
        :subregion="country.subregion"
        :flag="country.flags.png"
      />
    </li>
  </ul>
</template>

<style scoped></style>
