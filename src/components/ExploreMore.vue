<template>
  <section class="links">
    <router-link to="#" class="link-item">
      Erbjudanden
      <font-awesome-icon :icon="['fas', 'chevron-right']" />
    </router-link>
    <router-link to="#" class="link-item">
      Lagerbilar
      <font-awesome-icon :icon="['fas', 'chevron-right']" />
    </router-link>
    <router-link to="#" class="link-item">
      Bygg din volvo
      <font-awesome-icon :icon="['fas', 'chevron-right']" />
    </router-link>
    <router-link to="#" class="link-item">
      Begagnade bilar
      <font-awesome-icon :icon="['fas', 'chevron-right']" />
    </router-link>
  </section>
</template>

<script setup>
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";
import { fas } from "@fortawesome/free-solid-svg-icons";
import { library } from "@fortawesome/fontawesome-svg-core";
library.add(fas);
</script>

<style scoped>
.links {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 16px;
  font-weight: bolder;
  padding: 0 20px;
}

.link-item {
  font-weight: 900;
}
</style>
