<template>
  <div class="contain">
    <section
      class="hero"
      alt="Hero Image"
      :style="{ backgroundImage: `url(${heroImg})` }"
    >
      <div class="overlay"></div>
      <div class="content">
        <h2>Möt nya XC90</h2>
        <h1>Bilen med en plan B</h1>

        <p>Köp från 994 00 kr</p>
      </div>
    </section>
  </div>
</template>

<script setup>
import heroImg from "@/assets/hero1.jpg";
</script>

<style scoped>
.contain {
  position: relative;
  display: block;
}
.hero {
  display: block;
  width: 100%;
  height: 400px;
  background-size: cover;
}

.overlay {
  position: absolute;
  background-color: rgba(116, 113, 110, 0.45);
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  filter: brightness(0.8);
}

.content {
  position: absolute;
  display: flex;
  flex-direction: column;
  place-content: center;
}

h1 {
  font-weight: 600;
  color: rgb(255, 255, 255);
}
</style>
