<script setup>
import { defineProps } from 'vue';
const { quize } = defineProps(['quize']);
</script>

<template>
  <li class="card">
    <img class="card-img" :src="quize.img" alt="Math" />
    <div class="card-text">
      <h2 class="card-title">{{ quize.name }}</h2>
      <p>{{ quize.questions.length }} questions</p>
    </div>
  </li>
</template>

<style scoped>
.card {
  width: 310px;
  overflow: hidden;
  border-radius: 2%;
  box-shadow: 1px 1px 10px rgba(0, 0, 0, 0.1);
  margin-bottom: 35px;
  margin-right: 20px;
  cursor: pointer;
}

.card-img {
  display: block;
  width: 100%;
  height: 190px;
}

.card-text {
  padding: 0 5px;
}
</style>
