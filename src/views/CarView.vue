<script setup>
import { defineProps, ref, watch } from 'vue';
import { useRoute, useRouter, RouterView } from 'vue-router';
import cars from "../data/cars.json";

const route = useRoute();
const router = useRouter();

const id = route.params.id;

// get the car
const car =  cars.find(car => car.id === parseInt(id))

const getContact = () => {
  if(id == "6") {
    console.log(`No Contact for cardID: ${id}`);
    return;
  }
  return router.push(`/cars/${id}/contact`);
}

</script>

<template>
  <div v-if="car">
    <h1>Car View</h1>
    <!-- {{ car }} -->
    <p>{{ car.name }}</p>
    <p>Year: {{ car.year }}</p>
    <p>KM: {{ car.year }}</p>
    <p>Price: {{ car.price }}</p>
    <button @click="getContact" >Contact Us</button>
    <RouterView />
  </div>
  <div v-else>
    <h1>Car not found!</h1>
  </div>
</template>

<style scoped>

</style>