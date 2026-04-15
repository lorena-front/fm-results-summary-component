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
        <div v-for="data in content" :key="data.category" class="card-list" :class="data.category.toLocaleLowerCase()">
          <div class="left">
            <img :src="data.icon" alt="">
            <h3>{{ data.category }}</h3>
          </div>
          <span><span class="span-two">{{ data.score }}</span> / 100</span>
        </div>
        <button>
          Continue
        </button>
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
  height: 26rem;
  text-align: center;
  gap: 3rem;
  background: linear-gradient(to bottom,
      hsl(252, 100%, 67%),
      hsl(241, 81%, 54%));
  padding: 2.5rem;
  color: white;
  border-radius: 2rem;
  position: relative;
  z-index: 2;
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

.card-two {
  display: flex;
  align-items: center;
  flex-direction: column;
  width: 20rem;
  height: 26rem;
  text-align: center;
  gap: 1rem;
  padding: 2.5rem;
  border-top-right-radius: 2rem;
  border-bottom-right-radius: 2rem;
  background-color: white;
  position: relative;
  z-index: 1;
  margin-left: -30px;
}

.card-two p {
  align-self: flex-start;
  font-weight: 600;
  color: hsl(224, 30%, 27%);
  font-size: 1.2rem;
}

.card-list {
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 100%;
  padding: 1rem;
}

.left {
  display: flex;
  gap: 0.5rem;
}

.span-two {
  color: black;
  font-weight: 600;
}

.card-list {
  color: hsl(228.74deg 7.36% 48.41%);
}

.left h3 {
  font-size: 1rem;
}

.reaction,
.memory,
.verbal,
.visual {
  border-radius: 1rem;
}

.reaction {
  background-color: hsl(0, 100%, 97%);
}

.reaction h3 {
  color: hsl(0, 100%, 67%);
}

.memory {
  background-color: hsl(39, 100%, 97%);
}

.memory h3 {
  color: hsl(39, 100%, 56%);
}

.verbal {
  background-color: hsl(166, 100%, 97%);
}

.verbal h3 {
  color: hsl(166, 100%, 37%);
}

.visual {
  background-color: hsl(234, 85%, 97%);
}

.visual h3 {
  color: hsl(234, 85%, 45%);
}

button {
  padding: 1rem 5rem;
  border-radius: 2rem;
  border: none;
  background-color: hsl(224, 30%, 27%);
  color: white;
  cursor: pointer;
  font-weight: 600;
}

button:hover {
  background: linear-gradient(to bottom,
      hsl(252, 100%, 67%),
      hsl(241, 81%, 54%));
}
</style>
