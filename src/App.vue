<template>
  <div id="app">
    <NavBar :location-hash="locationHash" />
    
    <!-- Các sections của trang -->
    <section id="carousel">
      <CarouselSection />
    </section>
    <section id="event">
      <EventSection />
    </section>
    <section id="registration">
      <RegistrationSection />
    </section>
    <section id="gift">
      <GiftSection />
    </section>
    <section id="thank-you">
      <ThankYouSection />
    </section>

    <!-- Chat Button -->
    <button class="chat-button" @click="openChat">
      Chat with us
    </button>

    <!-- Chatfuel Script -->
    <script id="6738b4b97ce5457598f9ba30" src="https://dashboard.chatfuel.com/integration/entry-point.js" async defer></script>
  </div>
</template>

<script setup>
import CarouselSection from "./components/CarouselSection.vue";
import GiftSection from "./components/GiftSection.vue";
import ThankYouSection from "./components/ThankYouSection.vue";
import RegistrationSection from "./components/RegistrationSection.vue";
import NavBar from "./components/NavBar.vue";
import EventSection from "./components/EventSection.vue";
import { onMounted, ref } from "vue";

const locationHash = ref("");

function changeLocationHash() {
  let sections = Array.from(document.querySelectorAll("section"));
  const section = sections.find((s) => {
    const rect = s.getBoundingClientRect();
    return (
      rect.top <= window.innerHeight / 2 &&
      rect.bottom >= window.innerHeight / 2
    );
  });
  locationHash.value = `#${section.id}`;
}

onMounted(() => {
  changeLocationHash();
  window.addEventListener("scroll", changeLocationHash);
});

// Hàm mở chat khi click vào button (Chức năng mở Chatfuel)
function openChat() {
  window.Chatfuel.open();  // Gọi Chatfuel chatbot
}
</script>

<style scoped>
/* Định dạng button chat */
.chat-button {
  position: fixed;
  bottom: 20px;
  right: 20px;
  padding: 10px 20px;
  background-color: #007bff;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-size: 16px;
  z-index: 1000;
  box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.3);  /* Thêm bóng cho button */
}

.chat-button:hover {
  background-color: #0056b3;
}
</style>
