<script setup>
import content from '@/data/data.json'
import './style.css'
</script>

<template>
  <main>
    <div class="container">
      <div class="card-one">
        <p>Your Result</p>
        <h1>76
          <br><span class="card-one-span">of 100</span>
        </h1>
        <h2>Great</h2>
        <p>
          You scored higher than 65% of the people who have taken these tests.
        </p>
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
  text-align: center;
  gap: 1rem;
}

.card-one-span {
  font-size: 1rem;
  font-weight: 400;
}
</style>
