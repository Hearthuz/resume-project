<script setup lang="ts">
import SkillBox from './SkillBox.vue'
import ListIcon from './icons/ListIcon.vue'
import WidgetIcon from './icons/WidgetIcon.vue'
import skillsData from '../configs/skills.json'

import { ref } from 'vue'
import SwitchButton from './generic/SwitchButton.vue'

const show = ref(false)
</script>

<template>
  <header>
    <h1>Technical Skills</h1>
    <SwitchButton v-model="show">
      <template #iconLeft>
        <WidgetIcon style="color: black;" />
      </template>
      <template #iconRight>
        <ListIcon style="color: black;" />
      </template>
    </SwitchButton>
  </header>
  <main>
    <SkillBox :title="'Technical Language'" :skills="skillsData.technicalLanguage" :show="show" />
    <SkillBox :title="'Framework'" :skills="skillsData.framework" :show="show" />
    <SkillBox :title="'Other Tools'" :skills="skillsData.tools" :show="show" />
  </main>
</template>

<style scoped>
template {
  width: 100%;
  height: 100%;
}

header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 2rem;
}

main {
  width: 100%;
  height: 100%;
}

h1 {
  color: white;
}

.wrapper {
  background-color: rgba(255, 255, 255, 0.1);
  padding: 1rem;
  border-radius: 1rem;
}
</style>
