<template>
  <div class="content-container text-lg">
    <h1 class="h1">Showcase</h1>
    <p class="mb-4">
      Diese Seite zeigt Screenshots der sustAInableEducation Web-App, um einen
      Einblick zu erhalten.
    </p>
    <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
      <div v-for="(image, index) in images" :key="index">
        <Image :src="image" :alt="'Screenshot ' + index" preview />
      </div>
    </div>
  </div>
</template>

<script setup>
import Image from "primevue/image";

useSeoMeta({
  title: "Showcase",
});

const images = ref([]);

onMounted(() => {
  const imageFiles = import.meta.glob(
    "../public/img/showcase/*.{png,jpg,jpeg,svg}"
  );

  const categoryOrder = [
    "register",
    "login",
    "index",
    "profile",
    "overview",
    "space",
    "quiz",
  ];

  const allImages = [];
  for (const path in imageFiles) {
    imageFiles[path]().then((module) => {
      allImages.push(path.replace("../public", ""));

      if (allImages.length === Object.keys(imageFiles).length) {
        images.value = allImages.sort((a, b) => {
          const categoryA = extractCategory(a);
          const categoryB = extractCategory(b);

          const categoryIndexA = categoryOrder.indexOf(categoryA);
          const categoryIndexB = categoryOrder.indexOf(categoryB);

          if (categoryIndexA !== categoryIndexB) {
            return categoryIndexA - categoryIndexB;
          }

          return a.localeCompare(b);
        });
      }
    });
  }
});

function extractCategory(path) {
  const filename = path.split("/").pop();
  for (const category of [
    "register",
    "login",
    "index",
    "profile",
    "overview",
    "space",
    "quiz",
  ]) {
    if (filename.toLowerCase().startsWith(category)) {
      return category;
    }
  }
  return "other";
}
</script>
