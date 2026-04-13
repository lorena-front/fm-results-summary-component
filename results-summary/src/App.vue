<script setup>
import content from '@/data/data.json'
import './style.css'
</script>

<template>
  <main>
    <div class="container">
      <div class="card-one">
        <p>Your Result</p>
        <div class="score-wrapper">
          <div class="circle"></div>
          <h1>76</h1>
          <span class="card-one-span">of 100</span>
        </div>
        <div class="card-one-text">
          <h2>Great</h2>
          <p>
            You scored higher than 65% of the people who have taken these tests.
          </p>
        </div>
      </div>

      <div class="card-two">
        <p>Summary</p>
        <div v-for="data in content" :key="data.category" class="card-list">
          <h3>{{ data.category }}</h3>
          <span>{{ data.score }}</span>
          <img :src="data.icon" alt="">
        </div>
      </div>
    </div>
  </main>
</template>

<style scoped>
.container {
  display: flex;
}

.card-one {
  display: flex;
  align-items: center;
  flex-direction: column;
  width: 18rem;
  height: 23rem;
  text-align: center;
  gap: 3rem;
  background: linear-gradient(to bottom,
      hsl(252, 100%, 67%),
      hsl(241, 81%, 54%));
  padding: 2rem;
  color: white;
  border-radius: 2rem;
}

.score-wrapper {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
}

.score-wrapper h1 {
  font-size: 3rem;
  z-index: 1;
}

.circle {
  position: absolute;
  width: 135px;
  height: 135px;
  border-radius: 50%;
  background: linear-gradient(to bottom,
      hsla(256, 72%, 46%, 1),
      hsla(241, 72%, 46%, 0));
}

.card-one-span {
  font-size: 0.9rem;
  font-weight: 400;
}

.card-one-text {
  display: flex;
  gap: 1rem;
  flex-direction: column;
}

.card-one-text p,
.card-one p {
  width: 14rem;
  color: hsl(221, 100%, 96%);
}
</style>
