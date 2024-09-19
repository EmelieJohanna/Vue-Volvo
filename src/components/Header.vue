<template>
  <header class="header">
    <img :src="logo" alt="volvo logo" />
    <nav>
      <font-awesome-icon :icon="['far', 'user']" class="profile-icon" />
      <font-awesome-icon
        :icon="['fas', 'magnifying-glass']"
        class="search-icon"
      />
      <button><span class="menu">Meny</span></button>
    </nav>
  </header>
</template>

<script setup>
import logo from "@/assets/volvo-logo.svg";
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";
import { fas } from "@fortawesome/free-solid-svg-icons";
import { far } from "@fortawesome/free-regular-svg-icons";
import { library } from "@fortawesome/fontawesome-svg-core";
// Add the Font Awesome icon library
library.add(fas, far);
</script>

<style scoped>
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 60px;
  padding: 0 20px;
}

nav {
  display: flex;
  flex-direction: row;
  gap: 16px;
  align-items: center;
}

img {
  max-width: 25%;
}
.profile-icon {
  font-size: large;
  color: rgb(107, 101, 93);
}

.search-icon {
  font-size: large;
  color: rgb(107, 101, 93);
}

.menu {
  font-size: large;
}

button {
  border: none;
  background-color: none;
}
</style>
