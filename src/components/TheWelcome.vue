<script setup lang="ts">
import WelcomeItem from './WelcomeItem.vue'
import SkillBox from './SkillBox.vue'
import ListIcon from './icons/IconList.vue'
import skillsData from '../configs/skills.json'

import { ref } from 'vue'

const show = ref(false)
</script>

<template>
  <div>Technical Skills</div>
  <button @click="show = true">Icons</button>
  <button @click="show = false">List</button>
  <Transition>
    <div v-if="show">
      <SkillBox :skills="skillsData.technicalLanguage" />
      <SkillBox :skills="skillsData.framework" />
      <SkillBox :skills="skillsData.tools" />
      <WelcomeItem>
        <template #icon>
          <ListIcon />
        </template>
        <template #heading>Documentation</template>

        Vue’s
        <a href="https://vuejs.org/" target="_blank" rel="noopener">official documentation</a>
        provides you with all information you need to get started.
      </WelcomeItem>
    </div>
  </Transition>
</template>

<style scoped>
.wrapper {
  background-color: rgba(255, 255, 255, 0.5);
  padding: 1rem;
  border-radius: 1rem;
}

.v-enter-active,
.v-leave-active {
  transition: opacity 0.5s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}
</style>
