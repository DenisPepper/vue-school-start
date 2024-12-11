<template>
  <div class="container">
    <header>
      <h1>Quize</h1>
      <input type="text" placeholder="Search ..." />
    </header>
    <ul class="options-container">
      <li class="card">
        <img
          class="card-img"
          src="https://cdn0.youla.io/files/images/780_780/62/a8/62a87de4fac3891a4a0bb2f4-1.jpg"
          alt="Math"
        />
        <div class="card-text">
          <h2 class="card-title">Math</h2>
          <p>15 questions</p>
        </div>
      </li>
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

/* CARD */
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
  height: auto;
}

.card-text {
  padding: 0 5px;
}

.card-title {
}
</style>
