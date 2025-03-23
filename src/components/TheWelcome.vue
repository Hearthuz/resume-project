<script setup lang="ts">
import WelcomeItem from './WelcomeItem.vue'
import ItemBox from './ItemsBox.vue'
import DocumentationIcon from './icons/IconDocumentation.vue'

import { ref } from 'vue'

const show = ref(false)
</script>

<template>
  <div>Technical Skills</div>
  <button @click="show = true">Icons</button>
  <button @click="show = false">List</button>
  <Transition>
    <div v-if="show">
      <div class="wrapper">
        <ItemBox> </ItemBox>
      </div>
      <WelcomeItem>
        <template #icon>
          <DocumentationIcon />
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
.v-enter-active,
.v-leave-active {
  transition: opacity 0.5s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}
</style>
