<template>
<<<<<<< HEAD
  <div class="page-content">
    <div class="page-content-container">
      <h1>Badge</h1>
    </div>
=======
  <div class="page">
    <BadgeGenerator />
>>>>>>> f86f7e1 (feature: added basic BadgeGenerator component for personalized badge creation)
  </div>
</template>

<script>

import BadgeGenerator from '../components/Badges.vue'

export default {
  name: 'BadgeView'
  , components: {
    BadgeGenerator
  }
}
</script>

<style scoped>
h1 {
  font-size: var(--text-4xl);
  font-weight: 600;
  color: #000000;
}
</style>

