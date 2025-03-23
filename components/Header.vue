<template lang="html">
  <Menubar class="flex items-center justify-center" :model="items">
    <template #item="{ item, props, hasSubmenu }">
      <router-link
        v-if="item.route"
        v-slot="{ href, navigate }"
        :to="item.route"
        custom
      >
        <a v-ripple :href="href" v-bind="props.action" @click="navigate">
          <span :class="item.icon" />
          <span>{{ item.label }}</span>
        </a>
      </router-link>
      <a
        v-else
        v-ripple
        :href="item.url"
        :target="item.target"
        v-bind="props.action"
      >
        <span :class="item.icon" />
        <span>{{ item.label }}</span>
        <span v-if="hasSubmenu" class="pi pi-fw pi-angle-down" />
      </a>
    </template>
  </Menubar>
</template>
<script setup>
import { ref } from "vue";
import { useRouter } from "vue-router";

// const props = defineProps({
//   items: {
//     type: Array,
//     required: true,
//   },
// });
const router = useRouter();

const items = ref([
  {
    label: "Home",
    icon: "pi pi-home",
    route: "/",

    // items: [
    //   {
    //     label: "Styled",
    //     route: "/theming/styled",
    //   },
    //   {
    //     label: "Unstyled",
    //     route: "/theming/unstyled",
    //   },
    // ],
  },
  {
    label: "About me",
    icon: "pi pi-link",
    command: () => {
      router.push("/about");
    },
  },
  {
    label: "Contracts",
    icon: "pi pi-home",
    items: [
      {
        icon: "pi pi-github",
        label: "Github",
        url: "https://github.com/ColonyRabbit",
        target: "_blank",
      },
      {
        icon: "pi pi-envelope",
        label: "Gmail",
        url: "mailto:khanakorn01@gmail.com",
      },
    ],
  },
]);
</script>

<style lang=""></style>
