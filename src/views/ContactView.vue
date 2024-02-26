<script setup>
import { defineProps, ref, watch } from 'vue';
import { useRoute, RouterView } from 'vue-router';
import cars from "../data/cars.json";

const route = useRoute();

const id = route.params.id;
const car =  cars.find(car => car.id === parseInt(id));

</script>

<template>
  <div>
      <h1>Contact info</h1>
      Dealer: {{ car.contact.dealer }}
      
  </div>
  <div>
    Phone: {{ car.contact.number }}
  </div>
</template>

<style scoped>

</style>