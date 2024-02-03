<template>

    <h1 class=" mt-24 mx text-1xl font-extrabold leading-none tracking-tight md:text-2xl lg:text-3xl text-black">Class of {{props.people[0]["year"]}}</h1>
      <hr class="h-px mt-2 bg-gray-200 border-2 mx-auto dark:bg-gray-700 w-36 drop-shadow-2xl">
        <div class="lg:flex-cols-4 w-auto mt-3 lg:flex ml-3 mr-3 gap-5 flex-wrap flex-row sm:flex-cols-1 md:grid-cols-2 justify-evenly">
            <page_panel v-for="person in props.people" :info="person" />
        </div>
</template>

<script setup>

import page_panel from './page-panel.vue'

const props = defineProps(['people'])


</script>

<style scoped>
/* Your component's CSS code goes here */
</style>
