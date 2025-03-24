<script setup lang="ts">
const { skills } = defineProps<{ skills: { icon: string, label: string }[] }>()
</script>

<template>
    <div class="skill-box">
        <div v-for="({ icon, label }, index) in skills" :key="index" class="skill-item">
            <img :src="icon" alt="icon" />
            <p>{{ label }}</p>
        </div>
    </div>
</template>

<style>
.skill-box {
    background-color: rgba(0, 0, 0, 0.5);
    padding: 1rem;
    border-radius: 1rem;
    display: flex;
    align-items: center;
    flex-wrap: wrap;
    gap: 1rem;
}

.skill-item {
    display: flex;
    align-items: center;
    gap: 1rem;
}

.skill-item>p {
    font-weight: 600;
    font-size: 1.25rem;
}

.skill-item>img {
    height: 50px;
    width: 50px;
    object-fit: contain;
    object-position: center;
}
</style>