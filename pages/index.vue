<template>
  <div class="flex flex-col">
    <div class="background"></div>
    <section class="section two-col min-h-[calc(100vh-13rem)]">
      <div class="flex flex-col gap-8 lg:w-1/2">
        <h1
          class="font-bold text-5xl lg:text-7xl flex flex-col gap-2 relative h-28 lg:h-44"
        >
          <Transition name="word-animation">
            <span :key="wordPointer">{{ sustainableWords[wordPointer] }}</span>
          </Transition>
          <span class="text-primary-800 text-6xl lg:text-8xl"
            >sustainable.</span
          >
        </h1>
        <div class="text-2xl">
          Eigne dir nachhaltig Wissen über Nachhaltigkeit an. Mit unserer
          Web-App lernst du nicht nur, es macht sogar Spaß!
        </div>
        <div class="flex flex-wrap gap-2">
          <NuxtLink to="https://app.sustainable-edu.at/" target="_blank">
            <Button label="Zur Web-App" size="large" class="!text-xl !p-4" />
          </NuxtLink>
          <Button as="router-link" to="#fortschritt" text class="!text-xl !p-4">
            Fortschrittsberichte
            <MdiIcon icon="mdiArrowRight" />
          </Button>
        </div>
      </div>
      <img
        src="/img/hand-pflanze.png"
        alt="Hände mit Pflanze"
        class="-mr-24 lg:-mr-12 drop-shadow-2xl lg:max-w-[50%] lg:max-h-[calc(100vh-13rem)]"
      />
    </section>
    <section class="section-odd two-col-odd">
      <div class="flex flex-col gap-8 lg:w-1/2">
        <h2 class="h2">Lerne mit Stories</h2>
        <p class="text-2xl">
          <span class="font-bold">Lernen war noch nie so spaßig!</span>
          Eine gamifizierte Lernumgebung begleitet dich durch eine KI-Generierte
          Geschichte.
        </p>
        <p class="text-lg">
          <span class="font-bold">Ausgangslage.</span>
          Das Thema Nachhaltigkeit wird immer präsenter in unserer Gesellschaft.
          Deswegen ist eine Lernplattform hilfreich, welche die nachhaltige
          Aneignung von Wissen darüber ermöglicht. Die rapide Entwicklung von KI
          kann dabei als Chance genutzt werden. Deswegen soll unsere Arbeit eine
          gamifizierte, kollaborative Lernumgebung ermöglichen und eine noch
          nicht vorhandene Lernerfahrung etablieren.
        </p>
        <p class="text-lg">
          <span class="font-bold">Quizze.</span>
          Neben der Durchlebung einer Story mit verschiedenen
          Entscheidungspunkten und Abstimmungen, gibt es die Möglichkeit, nach
          Abschluss einer Lernumgebung sein Wissen mittels Quizze auf die Probe
          zu stellen.
        </p>
      </div>
      <img
        src="/img/hand-buch.png"
        alt="Hände mit Buch"
        class="-ml-24 lg:-mb-12 lg:mt-auto lg:-ml-12 drop-shadow-2xl flex-1 min-w-0"
      />
    </section>
    <section class="section flex flex-col justify-center items-center gap-12">
      <h2 class="h2">Unser Team</h2>
      <div class="flex justify-center flex-wrap gap-6">
        <Card class="w-80 overflow-hidden text-center" v-for="m in team">
          <template #header>
            <img :src="m.picture" :alt="'Portrait von ' + m.name" />
          </template>
          <template #title>{{ m.name }}</template>
          <template #subtitle>{{ m.role }}</template>
          <template #content>
            <div class="flex justify-center items-center gap-2 mt-1.5">
              <a :href="'mailto:' + m.email">
                <MdiIcon icon="mdiEmail" class="size-5" />
                <span class="sr-only">E-Mail an {{ m.name }}</span>
              </a>
              <a :href="m.github" target="_blank">
                <MdiIcon icon="mdiGithub" class="size-5" />
                <span class="sr-only">Github von {{ m.name }}</span>
              </a>
              <a :href="m.linkedin" target="_blank">
                <MdiIcon icon="mdiLinkedin" class="size-5" />
                <span class="sr-only">Linkedin von {{ m.name }}</span>
              </a>
            </div>
          </template>
        </Card>
      </div>
      <div class="text-xl">
        <span class="font-bold">Betreuer:</span>
        Prof. Ing. Dr.techn. Dominik Dolezal, BSc BEd MSc
      </div>
    </section>
    <section
      class="section-odd flex flex-col justify-center items-center gap-12"
    >
      <h2 class="h2">Meilensteine</h2>
      <div class="w-full">
        <Timeline
          :value="milestones"
          class="customized-timeline"
          align="alternate"
        >
          <template #marker="slotProps">
            <MdiIcon
              icon="mdiCheck"
              :class="slotProps.item.completed ? 'bg-primary' : 'bg-slate-200'"
              class="size-8 p-1 text-white rounded-full"
            />
          </template>
          <template #content="slotProps">
            <div class="h-8 flex flex-col justify-center">
              <h3 class="text-primary text-lg">{{ slotProps.item.date }}</h3>
            </div>
            <p>{{ slotProps.item.milestone }}</p>
          </template>
        </Timeline>
      </div>
    </section>
    <section
      id="fortschritt"
      class="section flex flex-col justify-center items-center gap-12"
    >
      <h2 class="h2">Fortschritts&shy;berichte</h2>
      <div class="flex flex-col gap-4">
        <nuxt-link v-for="report in displayedReports" :to="report._path">
          <Card>
            <template #title>
              <div class="flex justify-between">
                <span class="font-bold">{{ report.title }}</span>
                <MdiIcon icon="mdiArrowRight" />
              </div>
            </template>
            <template #subtitle>{{ report.date }}</template>
            <template #content>{{ report.description }}</template>
          </Card>
        </nuxt-link>
      </div>
      <Button
        @click="loadMoreReports"
        v-if="displayedReportsCount < filteredReports.length"
        label="Mehr anzeigen"
      />
    </section>
  </div>
</template>

<script setup>
import Button from "primevue/button";
import Card from "primevue/card";
import Timeline from "primevue/timeline";

useSeoMeta({
  title: "sustAInableEducation",
});

const sustainableWords = ["Study", "Think", "Be"];
const wordPointer = ref(0);
const sustainableWordChangeInterval = ref(null);
onNuxtReady(() => {
  sustainableWordChangeInterval.value = setInterval(() => {
    if (wordPointer.value >= sustainableWords.length - 1) wordPointer.value = 0;
    else wordPointer.value++;
  }, 4000);
});
onBeforeUnmount(() => {
  clearInterval(sustainableWordChangeInterval.value);
});

const progressReports = await queryContent("fortschritt").find();
const filteredReports = computed(() =>
  progressReports.toSorted((a, b) => {
    try {
      const [d1, m1, y1] = a.date.split(".");
      const [d2, m2, y2] = b.date.split(".");
      return new Date(y2, m2 - 1, d2) - new Date(y1, m1 - 1, d1);
    } catch (error) {
      return 0;
    }
  })
);
const displayedReportsCount = ref(3);
const loadMoreReports = () => {
  displayedReportsCount.value += 3;
};
const displayedReports = computed(() =>
  filteredReports.value.slice(0, displayedReportsCount.value)
);

const team = [
  {
    picture: "/img/edlinger.jpg",
    name: "Benjamin Edlinger",
    role: "Projektleiter, KI-Content-Entwickler",
    email: "bedlinger@student.tgm.ac.at",
    github: "https://github.com/bedlinger",
    linkedin: "https://www.linkedin.com/in/benjamin-edlinger-930169314/",
  },
  {
    picture: "/img/muehlboeck.jpg",
    name: "Leo Mühlböck",
    role: "Backend-Entwickler",
    email: "lmuehlboeck@student.tgm.ac.at",
    github: "https://github.com/lmuehlboeck",
    linkedin: "https://www.linkedin.com/in/leo-m%C3%BChlb%C3%B6ck-1bb5b3229/",
  },
  {
    picture: "/img/list.jpg",
    name: "Leander List",
    role: "Frontend-Entwickler",
    email: "llist@student.tgm.ac.at",
    github: "https://github.com/leanderlist",
    linkedin: "https://www.linkedin.com/in/leander-list-424110333/",
  },
  {
    picture: "/img/bohaczyk.jpg",
    name: "Kacper Bohaczyk",
    role: "KI-Quiz-Entwickler",
    email: "kbohaczyk@student.tgm.ac.at",
    github: "https://github.com/kaperbm",
    linkedin: "https://www.linkedin.com/in/kacper-bohaczyk-68127a258/",
  },
];
const milestones = [
  {
    date: "24.09.2024",
    milestone:
      "Wahl der zu verwendenden Technologien fixiert, Machbarkeit abgeschlossen",
    completed: true,
  },
  {
    date: "15.10.2024",
    milestone:
      "Mockup der Website fertiggestellt, Datenbank aufgesetzt, Benutzernamen Erstellung fertiggestellt",
    completed: true,
  },
  {
    date: "08.11.2024",
    milestone:
      "Prototyp der Website fertiggestellt, Prototyp der Story Generierung fertiggestellt",
    completed: true,
  },
  {
    date: "10.12.2024",
    milestone:
      "Usability Tests durchgeführt, Prototyp der Quiz Generierung fertiggestellt",
    completed: true,
  },
  {
    date: "26.01.2025",
    milestone:
      "Beta-Version der Website, Backend und Prompts zur Generierung fertiggestellt",
    completed: true,
  },
  {
    date: "18.02.2025",
    milestone: "Testing und Fehlerbehebung abgeschlossen",
    completed: true,
  },
];
</script>

<style scoped>
.customized-timeline .p-timeline-event-content {
  text-align: left;
}

.customized-timeline .p-timeline-event-opposite {
  flex: 0;
}

.word-animation-enter-active {
  transition: all 0.3s ease-out;
}

.word-animation-enter-from {
  transform: translateX(-4rem);
  opacity: 0;
}

.word-animation-enter-to {
  opacity: 1;
}

.word-animation-leave-active {
  transition: all 0.2s ease-in;
  position: absolute;
}

.word-animation-leave-from {
  opacity: 1;
}

.word-animation-leave-to {
  transform: translateX(4rem);
  opacity: 0;
  position: absolute;
}
</style>
