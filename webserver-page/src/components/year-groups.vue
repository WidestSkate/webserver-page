<template>

    <h1 class=" mt-24 mb-8 mx text-1xl font-extrabold leading-none tracking-tight md:text-2xl lg:text-3xl text-white">Class of 2024</h1>

        <div class="lg:flex-cols-4 w-auto mt-3 lg:flex ml-3 mr-3 gap-5 flex-wrap flex-row sm:flex-cols-1 md:grid-cols-2 justify-evenly">

            <page_panel v-for="name in names" :name="name" />

        </div>
</template>

<script setup>

import page_panel from './page-panel.vue'

const names = [
  "Alice",
  "Bob",
  "Charlie",
  "David",
  "Eva",
  "Frank",
  "Grace",
  "Henry",
  "Ivy",
  "Jack",
  "Katie",
  "Liam",
  "Mia",
  "Noah",
  "Olivia",
  "Peter",
  "Quinn",
  "Rachel",
  "Samuel",
  "Taylor"
];

</script>

<style scoped>
/* Your component's CSS code goes here */
</style>
