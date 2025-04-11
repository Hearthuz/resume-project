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
  <div class="skill-wrapper">
    <div class="header">
      <h1>Technical Skills</h1>
      <SwitchButton v-model="show">
        <template #iconLeft>
          <WidgetIcon style="color: black" />
        </template>
        <template #iconRight>
          <ListIcon style="color: black" />
        </template>
      </SwitchButton>
    </div>
    <div class="body">
      <SkillBox :title="'Technical Language'" :skills="skillsData.technicalLanguage" :show="show" />
      <SkillBox :title="'Framework'" :skills="skillsData.framework" :show="show" />
      <SkillBox :title="'Other Tools'" :skills="skillsData.tools" :show="show" />
    </div>
  </div>
</template>

<style scoped>
.skill-wrapper {
  width: 100%;
  height: 100%;
}

.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 2rem;
}
</style>
