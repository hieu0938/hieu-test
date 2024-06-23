<script setup>
import EventDetail from "./EventDetail.vue";
import EventCalendar from "./EventCalendar.vue";
import SectionHeader from "./SectionHeader.vue";
</script>

<template>
  <div class="flex flex-col items-center justify-center py-16 md:py-24">
    <SectionHeader title="Sự kiện cưới">
      ...tình yêu không phải là nhìn chằm chằm vào nhau, mà là nhìn chằm chằm về
      cùng một hướng...
    </SectionHeader>
    <div class="flex flex-col gap-4 md:flex-row md:justify-center">
      <EventDetail
        address="map1"
        class="order-0 md:order-first md:basis-[20%]"
        img-src="./groom-hometown.jpg"
        maps-url="https://maps.app.goo.gl/ps6CPVCUGyCBKSsJ9"
        time="16:00 31/12/2023"
        title="TIỆC CƯỚI NHÀ CHÚ RỂ"
      />
      <EventCalendar class="md:order-0 order-first basis-[60%]" />
      <EventDetail
        address="Map2"
        class="md:basis-[20%]"
        img-src="./bride-hometown.jpg"
        maps-url="https://maps.app.goo.gl/ps6CPVCUGyCBKSsJ9"
        time="15:30 30/12/2023"
        title="TIỆC CƯỚI NHÀ CÔ DÂU"
      />
    </div>
  </div>
</template>
