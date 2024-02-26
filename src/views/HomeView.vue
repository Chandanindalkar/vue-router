<script setup>
import { RouterLink } from 'vue-router';
import cars from "../data/cars.json";
</script>

<template>
  <div>
    <!-- <h1>stopped at 4:23:00</h1> -->
    <h1>Homepage</h1>
    <div class="cars">
      <RouterLink 
        v-for="car in cars" 
        :key="car.id"
        :to="`/cars/${car.id}`">
        {{ car.name }}
      </RouterLink>
    </div>
  </div>
</template>

<style scoped>
  .cars {
    display: flex;
  }
  .cars a {
    text-decoration: none;
    color: rgb(167, 162, 162);
    width: 100%;
    box-shadow: 1px 1px rgb(119, 114, 114);
    margin: 10px;
    text-align: center;
  }
</style>