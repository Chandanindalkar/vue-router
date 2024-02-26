<script setup>
import { defineProps, ref, watch } from 'vue';
import { useRoute, useRouter, RouterView } from 'vue-router';
import cars from "../data/cars.json";

const route = useRoute();
const router = useRouter();

const id = route.params.id;

const car =  cars.find(car => car.id === parseInt(id))

</script>

<template>
  <div>
    <h1>Car View</h1>
    <!-- {{ car }} -->
    <p>{{ car.name }}</p>
    <p>Year: {{ car.year }}</p>
    <p>KM: {{ car.year }}</p>
    <p>Price: {{ car.price }}</p>
    <button @click="router.push(`/cars/${id}/contact`)" >Contact Us</button>
    <RouterView />
  </div>
</template>

<style scoped>

</style>