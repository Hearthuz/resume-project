<script setup lang="ts">
const { title, skills, show } = defineProps<{ title: string, skills: { icon: string, label: string }[], show: boolean }>()

</script>

<template>
    <h2>{{ title }}</h2>
    <div class="skill-box" :style="{ width: show ? '100%' : 'fit-content' }">
        <div v-for="({ icon, label }, index) in skills" :key="index" class="skill-item">
            <img :src="icon" alt="icon" />
            <Transition name="slide-fade">
                <p v-if="show">{{ label }}</p>
            </Transition>
        </div>
    </div>
</template>

<style scoped>
h2 {
    font-size: 1.5rem;
    font-weight: 600;
    color: white;
}

.skill-box {
    background-color: rgba(255, 255, 255, 0.75);
    padding: 1rem;
    border-radius: 1rem;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr 1fr 1fr;
    gap: 1rem;
    transition: all 0.5s ease;
}

@media only screen and (max-width: 600px) {
    .skill-box {
        background-color: rgba(255, 255, 255, 0.75);
        padding: 1rem;
        border-radius: 1rem;
        display: grid;
        grid-template-columns: 1fr 1fr;
        gap: 1rem;
        transition: all 0.5s ease;
    }
}

.skill-item {
    gap: 0.5rem;
    display: flex;
    align-items: center;
}

.skill-item>p {
    font-weight: 600;
    font-size: 1rem;
}

.skill-item>img {
    height: 50px;
    width: 50px;
    object-fit: contain;
    object-position: center;
    border-radius: 10px;
}

.slide-fade-enter-active,
.slide-fade-leave-active {
    transition: all 0.25s ease;
}

.slide-fade-enter-from {
    transform: translateX(-100%);
    opacity: 0;
}

.slide-fade-leave-to {
    transform: translateX(-100%);
    opacity: 0;
}
</style>