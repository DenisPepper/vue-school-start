<script setup></script>

<template>
  <li class="card">
    <img
      class="card-img"
      src="https://cdn0.youla.io/files/images/780_780/62/a8/62a87de4fac3891a4a0bb2f4-1.jpg"
      alt=""
    />
    <div class="card-text">
      <h2 class="card-title">Title</h2>
      <p>count of questions</p>
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
