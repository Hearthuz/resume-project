<template>
    <div class="profile-wrapper">
        <div class="profile-content">
            <p>Name : </p>
            <p>Ariya Watchara-apanukorn</p>
            <p>Age : </p>
            <p>22</p>
            <p>Full-stack Developer</p>
        </div>
    </div>
</template>

<style>
.profile-wrapper {
    position: fixed;
    flex: 1;
}

.profile-content {
    width: 300px;
    background-color: rgba(255, 255, 255, 0.75);
    padding: 1rem;
    border-radius: 1rem;
    gap: 1rem;
    transition: all 1s ease;
    margin-bottom: 1rem;
    filter: drop-shadow(0 9px 7px rgb(0 0 0 / 0.1));
}
</style>