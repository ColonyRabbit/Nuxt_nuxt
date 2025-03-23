<template>
  <div class="card overflow-x-auto">
    <!-- Skills -->
    <OrganizationChart :value="Skills">
      <template class="bg-green-500" #default="slotProps">
        <span v-html="slotProps.node.label"></span>
      </template>
    </OrganizationChart>
    <!-- Tools -->
    <OrganizationChart class="" :value="Tools">
      <template class="bg-green-500" #default="slotProps">
        <span v-html="slotProps.node.label"></span>
      </template>
    </OrganizationChart>
  </div>
</template>

<script setup>
import { ref } from "vue";
import "primeicons/primeicons.css";

const Skills = ref({
  label: "Skills",
  children: [
    {
      label: "Front-End",
      children: [
        {
          label: "JavaScript",
        },
        {
          label: "TypeScript",
        },
        {
          label: "lib",
          children: [
            {
              label: "react",
            },
            {
              label: "vue(Learning)",
            },
          ],
        },
        {
          label: "Framework",
          children: [
            {
              label: "Next.js",
            },
            {
              label: "Nuxt.js(Learning)",
            },
          ],
        },
        {
          label: "CSS",
          children: [
            {
              label: "Tailwind CSS",
            },
            {
              label: "Bootstrap",
            },
          ],
        },
      ],
    },
    {
      label: "Back-End",
      children: [
        {
          label: "Runtime Environment",
          children: [
            {
              label: "Node.js",
            },
            {
              label: "Express.js",
            },
          ],
        },
        {
          label: "Database",
          children: [
            {
              label: "MongoDB",
            },
            {
              label: "FireBase",
            },
            {
              label: "SQL",
            },
          ],
        },
      ],
    },
  ],
});
const Tools = ref({
  label: "Tools",
  children: [
    {
      label: "API Test",
      children: [
        {
          label: "Postman",
        },
      ],
    },
    {
      label: "Containers",
      children: [
        {
          label: "Docker",
        },
      ],
    },
    {
      label: "Version Control",
      children: [
        {
          label: "Git",
        },
      ],
    },
    {
      label: "Communication",
      children: [
        {
          label: "Slack",
        },
      ],
    },
    {
      label: "Project Management",
      children: [
        {
          label: "Jira",
        },
      ],
    },
  ],
});
</script>
