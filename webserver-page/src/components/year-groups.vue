<template>

    <h1 class=" mt-24 mb-8 mx text-1xl font-extrabold leading-none tracking-tight md:text-2xl lg:text-3xl text-white">Class of 2024</h1>

        <div class="lg:flex-cols-4 w-auto mt-3 lg:flex ml-3 mr-3 gap-5 flex-wrap flex-row sm:flex-cols-1 md:grid-cols-2 justify-evenly">
            <page_panel v-if="loaded" v-for="name in fileContent" :info="name" />
        </div>
</template>

<script setup>

import page_panel from './page-panel.vue'
import { onMounted, ref} from 'vue';

var fileContent = null;
var loaded = ref(false)

onMounted(() => {
    readTextFile('/data.txt');
});

async function readTextFile(filePath) {
      try {
        const response = await fetch(filePath);
        if (!response.ok) {
          throw new Error('Failed to fetch the file');
        }
        const content = await response.text();
        fileContent = JSON.parse(content);
        console.log(fileContent)
        loaded.value = true
        console.log(loaded)
      } catch (error) {
        console.error('Error reading the file:', error);
      }
    }


</script>

<style scoped>
/* Your component's CSS code goes here */
</style>
