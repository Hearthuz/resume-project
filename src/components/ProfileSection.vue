<script setup lang="ts">
import GithubIcon from './icons/GithubIcon.vue'
import LinkedinIcon from './icons/LinkedinIcon.vue'
import CalendarIcon from './icons/CalendarIcon.vue'
import LocationIcon from './icons/LocationIcon.vue'
import MailIcon from './icons/MailIcon.vue'
import PhoneIcon from './icons/PhoneIcon.vue'

const handleButtonClick = (link: string) => {
  window.open(link)
}
</script>

<template>
  <div class="profile-wrapper">
    <div class="profile-content">
      <div class="top-box">
        <img
          class="profile-image"
          src="https://i.natgeofe.com/k/093c14b4-978e-41f7-b1aa-3aff5d1c608a/gray-wolf-closeup_3x4.jpg"
        />
        <h5>Ariya Watchara-apanukorn</h5>
        <div class="badge">Full-stack Developer</div>
        <div class="icons-box">
          <button class="icon" @click="handleButtonClick('https://google.com')">
            <GithubIcon />
          </button>
          <button class="icon" @click="handleButtonClick('https://google.com')">
            <LinkedinIcon />
          </button>
        </div>
      </div>
      <div class="contact-info under-box">
        <div>
          <CalendarIcon />
          November 3, 2002
        </div>
        <div>
          <LocationIcon />
          Bangkok, Thailand
        </div>
        <div>
          <MailIcon />
          ariya.watcharaapanukorn@gmail.com
        </div>
        <div>
          <PhoneIcon />
          +66 90-941-9895
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.profile-wrapper {
  position: relative;
  flex: 1;
}

@media (min-width: 1024px) {
  .profile-wrapper {
    position: fixed;
  }
}

.profile-content {
  transition: all 1s ease;
  filter: drop-shadow(0 9px 7px rgb(0 0 0 / 0.1));
}

.top-box {
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 1rem;
  background-color: rgba(255, 255, 255, 0.75);
  border-top-left-radius: 1rem;
  border-top-right-radius: 1rem;
}

.under-box {
  padding: 1rem;
  background-color: rgb(200, 200, 200, 0.75);
  border-bottom-left-radius: 1rem;
  border-bottom-right-radius: 1rem;
}

.profile-image {
  height: 150px;
  width: 150px;
  object-fit: cover;
  object-position: center;
  border-radius: 20px;
  padding: 2px;
  margin-top: -75px;
  margin-inline: auto;
}

.badge {
  background-color: rgb(65, 65, 65);
  padding-inline: 20px;
  padding-block: 10px;
  text-align: center;
  border-radius: 2rem;
  color: #fff;
  font-weight: 600;
  font-size: 1rem;
  width: fit-content;
  margin-inline: auto;
}

.icons-box {
  margin-top: 10px;
  display: flex;
  justify-content: center;
  gap: 10px;
}

.contact-info {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.contact-info div {
  display: flex;
  align-items: center;
  gap: 15px;
  color: #000;
}

.contact-info svg {
  width: 25px;
  height: 25px;
  display: flex;
  align-items: center;
  justify-content: center;
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
