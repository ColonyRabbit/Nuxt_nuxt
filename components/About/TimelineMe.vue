<template>
  <div class="card">
    <h1 class="text-2xl font-bold p-4 text-center">
      Hi, my name is Khanakorn Kositkhongchana and I'm a Front-End Developer.
      <br />
      "I've been interning as a front-end developer for 4 months, so my work is
      still limited. I would like you to consider this. Learning is something
      normal for me, and if it will benefit me in the future, I'm happy to do
      it."
    </h1>
    <Timeline :value="events" align="alternate" class="customized-timeline">
      <template #marker="slotProps">
        <span
          class="flex w-8 h-8 items-center justify-center text-white rounded-full z-10 shadow-sm"
          :style="{ backgroundColor: slotProps.item.color }"
        >
          <i :class="slotProps.item.icon"></i>
        </span>
      </template>
      <template #content="slotProps">
        <Card class="mt-4">
          <template #title>
            {{ slotProps.item.status }}
          </template>
          <template #subtitle>
            {{ slotProps.item.date }}
          </template>
          <template #content>
            <img
              v-if="slotProps.item.image"
              :src="`https://primefaces.org/cdn/primevue/images/product/${slotProps.item.image}`"
              :alt="slotProps.item.name"
              width="200"
              class="shadow-sm"
            />
            <p v-html="slotProps.item.description"></p>

            <!-- <Button label="Read more" text></Button> -->
          </template>
        </Card>
      </template>
    </Timeline>
  </div>
</template>

<script setup>
import { ref } from "vue";
import "primeicons/primeicons.css";
const events = ref([
  {
    status: "Exhibition 19 MAR 2024",
    date: "19/03/2024",
    icon: "pi pi-users",
    color: "#9C27B0",
    description:
      "Rajamangala University of Technology Krungthep <br> I participated in a project proposal competition in the Faculty of Science and won first place.",
    image: "game-controller.jpg",
  },
  {
    status: "Internship experience",
    date: "11/11/2024 - 07/03/2025 ",
    icon: "pi pi-tag",
    description:
      "Project dealer: Managed the operation of B2B web applications for logistics business clients. Collaborated with different teams to develop and improve applications for business use. Fixed issues and optimized applications to run more efficiently and quickly. Added new features and improved user experience based on user feedback. Used data from applications to help make decisions for better performance and operations.",

    color: "#673AB7",
  },
]);
</script>

<style lang="scss" scoped>
@media screen and (max-width: 960px) {
  ::v-deep(.customized-timeline) {
    .p-timeline-event:nth-child(even) {
      flex-direction: row;

      .p-timeline-event-content {
        text-align: left;
      }
    }

    .p-timeline-event-opposite {
      flex: 0;
    }
  }
}
</style>
