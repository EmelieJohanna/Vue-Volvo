<template>
  <div class="contain">
    <section
      class="hero"
      alt="Hero Image"
      :style="{ backgroundImage: `url(${currentHeroImg})` }"
    >
      <div class="overlay"></div>
      <div class="content">
        <h2>Möt nya XC90</h2>
        <h1>Bilen med en plan B</h1>
        <p>Köp från 994 00 kr</p>
        <button>Utforska</button>
      </div>
    </section>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from "vue";
import smallHeroImg from "/images/hero-small.webp";
import wideHeroImg from "/images/hero-wide.webp";

// initial image
const currentHeroImg = ref(wideHeroImg);

function updateHeroImage() {
  if (window.innerWidth < 768) {
    currentHeroImg.value = smallHeroImg;
  } else {
    currentHeroImg.value = wideHeroImg;
  }
}

onMounted(() => {
  updateHeroImage();
  window.addEventListener("resize", updateHeroImage);
});

onUnmounted(() => {
  window.removeEventListener("resize", updateHeroImage);
});
</script>

<style scoped>
.contain {
  position: relative;
  display: block;
}

.hero {
  display: block;
  width: 100%;
  height: 500px;
  background-size: cover;
  background-position: center;
}

.overlay {
  position: absolute;
  background-color: rgba(170, 170, 207, 0.45);
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  filter: brightness(0.5);
}

.content {
  position: absolute;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  margin-top: 2rem;
  width: 100%;
  color: aliceblue;
  font-size: 1rem;
}

h1 {
  font-size: xx-large;
  font-weight: 600;
  color: rgb(255, 255, 255);
  margin-bottom: 0.5rem;
}

button {
  background-color: rgb(229, 234, 238);
  border: none;
  padding: 14px 30px;
  color: rgb(22, 21, 21);
  font-weight: 600;
  border-radius: 4px;
  margin-top: 10px;
  font-size: medium;
  cursor: pointer;
}

button:hover {
  background-color: rgb(173, 178, 184);
  transition: 0.2s;
}

button:active {
  background-color: rgb(147, 150, 155);
  transform: scale(0.9);
}
</style>
