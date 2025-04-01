<script setup lang="ts">
import GithubIcon from './icons/GithubIcon.vue';
import LinkedinIcon from './icons/LinkedinIcon.vue';

const handleButtonClick = (link: string) => {
    window.open(link)
}

</script>

<template>
    <div class="profile-wrapper">
        <img class="profile-image"
            src="https://images.unsplash.com/photo-1624397642005-4a8b6cb9b4ca?q=80&w=2574&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" />
        <div class="profile-content">
            <p><span>Name : </span>Ariya Watchara-apanukorn</p>
            <p><span>Age : </span> 22</p>
            <div class="badge">Full-stack Developer</div>
            <div class="flex-box">
                <button class="icon" @click="handleButtonClick('https://google.com')">
                    <GithubIcon />
                </button>
                <button class="icon" @click="handleButtonClick('https://google.com')">
                    <LinkedinIcon />
                </button>
            </div>
        </div>
    </div>
</template>

<style scoped>
.profile-wrapper {
    position: fixed;
    flex: 1;
}

.profile-content {
    width: 350px;
    background-color: rgba(255, 255, 255, 0.75);
    padding: 1rem;
    border-radius: 1rem;
    gap: 1rem;
    transition: all 1s ease;
    margin-bottom: 1rem;
    filter: drop-shadow(0 9px 7px rgb(0 0 0 / 0.1));
}

.profile-image {
    height: 150px;
    width: 150px;
    object-fit: cover;
    object-position: center;
    border-radius: 20px;
    padding: 2px;
}

.badge {
    background-color: rgb(65, 65, 65);
    padding-inline: 20px;
    padding-block: 10px;
    text-align: center;
    border-radius: 2rem;
    color: #FFF;
    font-weight: 600;
    font-size: 1rem;
    width: fit-content;
    margin-inline: auto;
}

.flex-box {
    margin-top: 20px;
    display: flex;
    justify-content: space-around;
    gap: 10px;
}

.icon {
    width: 50px;
    height: 50px;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    background: transparent;
    border: none;
    border-radius: 10px;
}

.icon:hover {
    background: rgb(218, 218, 218);
}
</style>