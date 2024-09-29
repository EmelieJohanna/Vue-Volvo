<template>
  <section class="container">
    <h2>Utvalda modeller</h2>
    <div class="content">
      <div class="info">
        <div class="text">
          <h3>{{ currentCar.model }}</h3>
          <h4>{{ currentCar.description }}</h4>
          <p>Köp från {{ currentCar.price }}kr</p>
          <button>Utforska</button>
        </div>
        <div class="nav-buttons">
          <!-- Not work if car nr  -->
          <button
            @click="prevCar"
            :disabled="currentIndex === 0"
            class="button"
          >
            <img :src="prevIcon" alt="arrow for going back" class="nav-icon" />
          </button>
          <!-- Not work if car id car.length -1  -->
          <button
            @click="nextCar"
            :disabled="currentIndex === cars.length - 1"
            class="button"
          >
            <img :src="nextIcon" alt="arrow forward" />
          </button>
        </div>
      </div>

      <!--  Here there's the car -->
      <div>
        <img :src="currentCar.img" :alt="currentCar.model" class="img" />
      </div>
      <!-- Here is a indicator that shows you how long you have slided for or clicked -->
      <div class="progress-bar">
        <div class="progress-track">
          <div
            :style="{
              left: leftPositionPercentage + '%',
              width: indicatorWidth + '%',
            }"
            class="progress-indicator"
          ></div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import nextIcon from "@/assets/forward.svg";
import prevIcon from "@/assets/nav-back.svg";
import { ref, computed } from "vue";
import jsonCarData from "@/data/cars.json";

const cars = ref(jsonCarData);
const currentIndex = ref(0);

const currentCar = computed(() => cars.value[currentIndex.value]);
// Navigation methods
const prevCar = () => {
  if (currentIndex.value > 0) {
    currentIndex.value--;
  }
};

const nextCar = () => {
  if (currentIndex.value < cars.value.length - 1) {
    currentIndex.value++;
  }
};

const indicatorWidth = computed(() => {
  return 100 / cars.value.length;
});

const leftPositionPercentage = computed(() => {
  const carouselProgress = currentIndex.value / (cars.value.length - 1);
  const availableTrackWidth = 100 - indicatorWidth.value;
  return carouselProgress * availableTrackWidth;
});
</script>

<style scoped>
.container {
  display: grid;
  grid-row: inherit;
  width: 100%;
  padding: 1rem;
}

.content {
  background-color: rgb(247, 247, 247);
  padding: 1rem;
}

.info {
  display: flex;
  justify-content: space-between;
}

.text button {
  background-color: rgb(29, 29, 29);
  border: none;
  padding: 14px 30px;
  color: rgb(238, 238, 238);
  font-weight: 600;
  border-radius: 4px;
  margin-top: 10px;
  font-size: medium;
  cursor: pointer;
}

h2 {
  font-weight: 700;
}

h3 {
  font-weight: 700;
}

h4 {
  font-size: 1.2rem;
  font-weight: 600;
  color: rgb(112, 112, 112);
}

p {
  font-size: 0.8rem;
}

button:hover {
  background-color: rgb(173, 178, 184);
  transition: 0.2s;
}

button:active {
  background-color: rgb(147, 150, 155);
  transform: scale(0.9);
}

.nav-buttons {
  display: flex;
  gap: 4px;
}

.button {
  justify-content: center;
  place-content: center;
  align-items: center;
  height: 2rem;
  width: 2rem;
  border: none;
  background-color: rgb(27, 27, 27);
  border-radius: 50%;
}

.img {
  max-width: 100%;
  height: auto;
  object-fit: contain;
  padding-top: 2rem;
}

.progress-bar {
  width: 100%;
  position: relative;
}

.progress-track {
  width: 100%;
  height: 1px;
  background-color: rgb(194, 194, 194);
}

.progress-indicator {
  position: absolute;
  height: 1px;
  background-color: rgb(0, 0, 0);
  transition: left 0.3s ease-in-out;
}
</style>
