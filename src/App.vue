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
  flex-direction: column;
  align-items: start;
  gap: 2rem;
}

.left-side {
  position: relative;
  min-width: 25rem;
  display: flex;
  justify-content: center;
  padding-top: calc(var(--section-gap) / 2);
}

.right-side {
  width: 100%;
  flex: 1;
  padding-top: calc(var(--section-gap) / 2);
}

@media (min-width: 1024px) {
  main {
    flex-direction: row;
  }

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
