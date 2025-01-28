<template>
  <div class="content-container text-lg">
    <h1 class="h1">Showcase</h1>
    <p class="mb-4">
      Diese Seite zeigt Screenshots der sustAInableEducation Web-App, um einen
      Einblick zu erhalten.
    </p>
    <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
      <div v-for="(image, index) in images" :key="index">
        <Image :src="image" alt="Image" preview />
      </div>
    </div>
  </div>
</template>

<script setup>
import Image from 'primevue/image';

useSeoMeta({
  title: "Showcase",
});

const images = ref([]);

onMounted(() => {
  const imageFiles = import.meta.glob("../public/img/showcase/*.{png,jpg,jpeg,svg}");
  for (const path in imageFiles) {
    imageFiles[path]().then((module) => {
      images.value.push(path.replace("../public", ""));
      images.value.sort();
    });
  }
});
</script>
