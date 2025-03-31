<script setup lang="ts">
const { title, skills, show } = defineProps<{ title: string, skills: { icon: string, label: string }[], show: boolean }>()

</script>

<template>
    <h2>{{ title }}</h2>
    <div class="skill-box">
        <div v-for="({ icon, label }, index) in skills" :key="index" class="skill-item"
            :style="{ 'justify-content': show ? 'start' : 'center' }">
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
    padding-bottom: 1rem;
}

.skill-box {
    background-color: rgba(255, 255, 255, 0.75);
    padding: 1rem;
    border-radius: 1rem;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr 1fr 1fr;
    gap: 1rem;
    transition: all 1s ease;
    margin-bottom: 1rem;
    filter: drop-shadow(0 9px 7px rgb(0 0 0 / 0.1));
}

.skill-item {
    gap: 0.5rem;
    display: flex;
    flex-direction: column;
    align-items: center;
}

.skill-item>p {
    font-weight: 500;
    font-size: 1rem;
}

.skill-item>img {
    height: 50px;
    width: 50px;
    object-fit: contain;
    object-position: center;
    border-radius: 10px;
    background-color: white;
    padding: 2px;
}

.slide-fade-enter-active,
.slide-fade-leave-active {
    transition: all 0.25s ease;
}

.slide-fade-leave-to,
.slide-fade-enter-from {
    transform: translateY(-100%);
    opacity: 0;
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
        width: 100%;
    }

    .skill-item>p {
        font-weight: 700;
        font-size: 0.75rem;
    }
}
</style>