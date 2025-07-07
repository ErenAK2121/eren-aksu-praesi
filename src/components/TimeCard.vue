<template>
  <v-container>
    <v-timeline side="end">
      <v-timeline-item
        v-for="(entry, index) in timelineData"
        :key="index"
        :dot-color="entry.color"
        :icon="entry.icon"
        fill-dot
      >
        <template #opposite>
          <strong>{{ entry.year }}</strong>
        </template>

        <template #default>
          <h3 class="text-h6 font-weight-bold mb-2">{{ entry.title }}</h3>
          <p>{{ entry.description }}</p>
        </template>
      </v-timeline-item>
    </v-timeline>
  </v-container>
</template>

<script setup>
const timelineData = [
  {
    year: '04/2013',
    title: 'Max Planck Realschule',
    description: 'Beginn meiner schulischen Laufbahn an der Max-Planck-Realschule in Köln-Porz.',
    icon: 'mdi-school',
    color: 'blue'
  },
  {
    year: 'ca. 2016',
    title: 'Erste Programmiererfahrungen',
    description: 'Erste Erfahrungen mit Java durch das Interesse an Minecraft-Plugin-Entwicklung.',
    icon: 'mdi-code-tags',
    color: 'green'
  },
  {
    year: '07/2019',
    title: 'Realschulabschluss',
    description: 'Fachoberschulreife mit Q-Vermerk an der Max-Planck-Realschule.',
    icon: 'mdi-school-outline',
    color: 'grey'
  },
  {
    year: '08/2019',
    title: 'Fachabitur am Georg-Simon-Ohm Berufskolleg',
    description: 'Beginn des Fachabiturs im Bereich Informations-/Elektrotechnik.',
    icon: 'mdi-electric-switch',
    color: 'yellow'
  },
  {
    year: '06/2021',
    title: 'Fachhochschulreife',
    description: 'Abschluss des Fachabiturs mit Note 2,1.',
    icon: 'mdi-certificate',
    color: 'amber'
  },
  {
    year: '09/2021',
    title: 'Studium: Wirtschaftsinformatik (B.Sc.)',
    description: 'Studium an der TH Köln mit Schwerpunkt auf Data Mining, Deep Learning und wissenschaftlicher Arbeit.',
    icon: 'mdi-laptop',
    color: 'indigo'
  },
  {
    year: '06/2022 – 06/2023',
    title: 'Werkstudent bei National Express',
    description: 'Python-Automatisierungen, Datenbankentwicklung und Unterstützung des Betriebs.',
    icon: 'mdi-train',
    color: 'cyan'
  },
  {
    year: '09/2023 – 03/2024',
    title: 'Praktikum bei Adesso SE',
    description: 'Fullstack-Webentwicklung mit VueJS & Spring Boot, Entwicklung von Banking-Modulen.',
    icon: 'mdi-bank',
    color: 'deep-purple'
  },
  {
    year: '07/2024 – heute',
    title: 'Wissenschaftliche Hilfskraft bei PMV',
    description: 'Entwicklung von GANs für synthetische Gesundheitsdaten, SQL/Pandas-Analysen.',
    icon: 'mdi-flask-outline',
    color: 'pink'
  },
  {
    year: '02/2025',
    title: 'Bachelorarbeit',
    description: 'Thema: Erstellung synthetischer Routinedaten im Gesundheitswesen mittels GANs.',
    icon: 'mdi-file-document-edit-outline',
    color: 'teal'
  }
]
</script>
