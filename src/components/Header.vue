<template>
  <header class="header">
    <img :src="logo" alt="volvo logo" />
    <nav>
      <img :src="avatar" alt="profile icon" class="profile-icon" />
      <img :src="search" alt="search icon" class="search-icon" />
      <!-- Font awesome -->
      <!-- <font-awesome-icon :icon="['far', 'user']" class="profile-icon" /> -->
      <!-- <font-awesome-icon
        :icon="['fas', 'magnifying-glass']"
        class="search-icon"
      /> -->

      <!-- Vue icons -->
      <!-- <Avatar alt="profile icon" class="profile-icon" />
      <Search alt="search icon" class="search-icon" /> -->
      <button><span class="menu">Meny</span></button>
    </nav>
  </header>
</template>

<script setup>
import logo from "@/assets/volvo-logo.svg";

import avatar from "@/assets/avatar-icon.svg";
import search from "@/assets/search-icon.svg";

// test, implement?
// import Avatar from "./icons/IconAvatar.vue";
// import Search from "./icons/IconSearch.vue";

// FontAwesome is in the past
// import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";
// import { fas } from "@fortawesome/free-solid-svg-icons";
// import { far } from "@fortawesome/free-regular-svg-icons";
// import { library } from "@fortawesome/fontawesome-svg-core";
// // Add the Font Awesome icon library
// library.add(fas, far);
</script>

<style scoped>
.header {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 999;
  background-color: white;
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
  color: black;
}

img {
  max-width: 25%;
}

.profile-icon {
  font-size: large;
}

.search-icon {
  font-size: large;
}

button {
  border: none;
  background-color: transparent;
}

.menu {
  font-size: large;
}
</style>
