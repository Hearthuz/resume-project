<script setup lang="ts">
import AboutMeSection from './components/AboutMeSection.vue'
import ProfileSection from './components/ProfileSection.vue'
import SkillSection from './components/SkillSection.vue'
import WorkExperienceSection from './components/WorkExperienceSection.vue'
</script>

<template>
  <main class="wrapper">
    <div class="left-side">
      <ProfileSection />
    </div>
    <div class="right-side">
      <AboutMeSection />
      <SkillSection />
      <WorkExperienceSection />
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
  margin-top: calc(var(--section-gap) / 2);
  margin-inline: 1rem;
  margin-bottom: 1rem;
  border-radius: 1rem;
  overflow: hidden;
  filter: drop-shadow(0 9px 7px rgb(0 0 0 / 0.1));
}

.right-side > div:nth-child(odd) {
  padding: 1.5rem;
  background-color: rgba(255, 255, 255, 0.75);
}

.right-side > div:nth-child(even) {
  padding: 1.5rem;
  background-color: rgb(200, 200, 200, 0.75);
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
