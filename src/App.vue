<template>
  <div class="counter">
    <h1 class="counter__header">Counter value is:</h1>
    <div class="counter__box">
      <h2 class="counter__value">0</h2>
      <button>-</button>
      <button>+</button>
    </div>
  </div>
</template>

<style>
.counter {
  max-width: 50vw;
  box-sizing: border-box;
  font-family: Verdana, Geneva, Tahoma, sans-serif;
  background-color: rgb(207, 197, 197);
}

.counter__header {
  text-align: center;
  margin: 0;
  padding: 0.5rem;
}

.counter__box {
  display: grid;
  grid-template-columns: repeat(2, max-content);
  justify-content: center;
}

.counter__value {
  grid-row: 1;
  grid-column: 1/-1;
  text-align: center;
}

button {
  grid-row: 2;

  width: 10rem;
  height: 3rem;
  padding: 0.5rem;

  display: flex;
  align-items: center;
  justify-content: center;

  background-color: black;
  color: goldenrod;
  border: none;

  font-size: 2rem;
}
</style>
