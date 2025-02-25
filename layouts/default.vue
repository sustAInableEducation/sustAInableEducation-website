<template>
  <div class="min-h-screen flex flex-col">
    <header class="flex justify-center py-2 h-28">
      <nuxt-link to="/" class="flex gap-2 items-center">
        <img
          src="/img/logo.svg"
          alt="sustAInableEducation Logo"
          class="size-24"
        />
        <div class="font-bold text-xl">sustAInableEducation</div>
      </nuxt-link>
    </header>
    <main class="flex-1">
      <slot />
    </main>
    <footer>
      <hr class="h-0.5 bg-primary-200" />
      <div class="p-12 flex flex-col items-center gap-8">
        <div class="flex gap-4">
          <nuxt-link
            to="https://github.com/sustAInableEducation/sustAInableEducation"
            target="_blank"
          >
            <MdiIcon icon="mdiGithub" class="size-10" />
            <span class="sr-only">Github Organistation vom Projekt</span>
          </nuxt-link>
          <nuxt-link to="https://www.tgm.ac.at/" target="_blank">
            <img src="/img/tgm-logo.png" alt="TGM" class="h-10" />
          </nuxt-link>
        </div>
        <div class="flex flex-col sm:flex-row gap-1 text-center sm:text-left"><span>
            <nuxt-link to="/impressum" class="link">Impressum</nuxt-link>
          </span>
          <span class="hidden sm:inline">|</span>
          <span>©{{ new Date().getFullYear() }} sustAInableEducation</span>
          <span class="hidden sm:inline">|</span>
          <span>
            <nuxt-link to="/showcase" class="link">Showcase</nuxt-link>
          </span>
        </div>
        <div class="flex gap-1">
          <Button
            as="router-link"
            to="#"
            @click="scrollToTop"
            text
            class="!text-xl"
          >
            Zurück nach oben
            <MdiIcon icon="mdiArrowUpThick" />
          </Button>
        </div>
      </div>
    </footer>
  </div>
</template>

<script setup>
import Button from "primevue/button";

const scrollToTop = () => {
  window.scrollTo({
    top: 0,
    behavior: "smooth",
  });
};
</script>

<style lang="scss" scoped></style>
