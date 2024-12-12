<script setup>
import quizesData from './data/quizes.json';
import { ref as useState, watch } from 'vue';
import Card from './components/card/Card.vue';

const quizes = useState(quizesData);
const search = useState('');

const filterQuizes = (value) => {
  quizes.value = quizesData.filter((item) => item.name.toLowerCase().includes(value.toLowerCase()));
};

watch(search, filterQuizes);
</script>

<template>
  <div class="container">
    <header>
      <h1>Quize</h1>
      <input v-model.lazy.trim="search" type="text" placeholder="Search ..." />
    </header>
    <ul class="options-container">
      <Card v-for="quize of quizes" :key="quize.id" :quize="quize" />
      <!--
      <li class="card" v-for="quize of quizes" :key="quize.id">
        <img class="card-img" :src="quize.img" alt="Math" />
        <div class="card-text">
          <h2 class="card-title">{{ quize.name }}</h2>
          <p>{{ quize.questions.length }} questions</p>
        </div>
      </li>
      -->
    </ul>
  </div>
</template>

<style scoped>
.container {
  max-width: 800px;
  margin: 0 auto;
}

header {
  margin-bottom: 10px;
  margin-top: 30px;
  display: flex;
  align-items: center;
}

header h1 {
  margin-right: 30px;
}

header input {
  border: none;
  border-radius: 4px;
  padding: 10px;
  background-color: rgba(128, 128, 128, 0.1);
}

.options-container {
  display: flex;
  flex-wrap: wrap;
  margin-top: 40px;
}
</style>
