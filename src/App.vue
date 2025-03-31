<script setup lang="ts">
import ProfileSection from './components/ProfileSection.vue';
import SkillSection from './components/SkillSection.vue'
</script>

<template>
  <main class="wrapper">
    <div class="left-side">
      <ProfileSection />
    </div>
    <div class="right-side">
      <SkillSection />
    </div>
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

main {
  width: 100%;
  position: relative;
  overflow-y: auto;
  display: flex;
  align-items: start;
}

.left-side {
  position: relative;
  min-width: 35%;
  display: flex;
  justify-content: center;
  padding-inline: calc(var(--section-gap) / 2);
  padding-block: calc(var(--section-gap) / 4);
}

.right-side {
  flex: 1;
  padding-inline: calc(var(--section-gap) / 2);
  padding-block: calc(var(--section-gap) / 4);
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }
}
</style>
