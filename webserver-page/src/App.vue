<script setup>
import year_groups from './components/year-groups.vue'
import { onMounted, ref} from 'vue';

var fileContent = null;
var loaded = ref(false)

onMounted(() => {
    readTextFile('/data.json');
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

<template>
  <img class="h-auto w-80 mx-auto my-12" src="/logo.png" alt="Ron Dearing Logo">
  <h1 class=" text-center mx-auto mb-12 text-4xl font-extrabold leading-none tracking-tight text-gray-900 md:text-5xl lg:text-6xl ">RDUTC Year 13 websites list</h1>
  <h2 class=" text-center mx-auto mb-12 text-lg leading-none tracking-tight text-gray-900 md:text-xl lg:text-2xl ">A place where year 13 RDUTC students website coursework is hosted locally for them to view</h2>
  <hr class="h-px mt-8 bg-gray-200 border-2 mx-auto dark:bg-gray-700 w-90">
  <year_groups v-if="loaded" v-for="year in fileContent" :people="year"/>
  <hr class="h-px my-8 bg-gray-200 border-1 mx-auto dark:bg-gray-700 w-full">
  <h5 class="mb-8 text-sm font-bold tracking-tight text-gray-900 ">Created by Zakk Amers-Delph Ex Student</h5>
</template>

<style scoped>
</style>
