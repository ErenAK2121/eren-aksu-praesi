<template>
  <div>
    <!-- Toggle Button -->
    <v-btn
      icon
      @click="open = !open"
      class="toggle-btn"
      :class="{ rotate: open }"
    >
      <v-icon>mdi-chevron-right</v-icon>
    </v-btn>

    <!-- Slide-in Card under header -->
    <transition name="slide">
      <v-card
        v-if="open"
        class="slide-card"
        elevation="8"
      >
        <v-card-title class="text-h6 font-weight-bold">
          Persönliche Infos
        </v-card-title>
        <v-card-text>
          <p>Geboren am 11.06.2003 in Köln-Porz</p>
          <p>22 Jahre alt</p>
          <br>
          <p>Meine Hobbys sind:</p>
          <p> - Basketball (BC Pesch 04)</p>
          <p> - Motorrad fahren</p>
          <p> - Programmieren</p>
          <br>
          <p>Familienstand: Ledig</p>
          <br>
          <p>Staatsangehörigkeit: Deutsch</p>
          <br>
          <p>Sprachkenntnisse:</p>
          <p> - Deutsch (Muttersprache)</p>
          <p> - Englisch (fließend)</p>
          <p> - Türkisch (Vatersprache)</p>
          <br>
          <p>Führerschein: Klasse B (PKW), Klasse A2 (Motorrad)</p>
        </v-card-text>
        <v-card-title class="text-h6 font-weight-bold">
          Kontakt
        </v-card-title>
        <v-card-text>
            E-Mail: eren-aksu@gmx.de
            <br>
            Telefon: +49 170 7756624
            <br>
            Anschrift: Eichendorffstr. 34, 51147 Köln
        </v-card-text>
      </v-card>
    </transition>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const open = ref(false)
</script>

<style scoped>
/* Toggle Button Position */
.toggle-btn {
  position: fixed;
  top: 220px; /* verschiebt ihn unter den Header */
  left: 10px;
  z-index: 900;
  transition: transform 0.3s ease;
}
.toggle-btn.rotate {
  transform: rotate(180deg);
}

/* Slide Transition */
.slide-enter-active,
.slide-leave-active {
  transition: all 0.4s ease;
}
.slide-enter-from {
  transform: translateX(-110%);
  opacity: 0;
}
.slide-enter-to {
  transform: translateX(0);
  opacity: 1;
}
.slide-leave-to {
  transform: translateX(-110%);
  opacity: 0;
}

/* Slide Card Design */
.slide-card {
  position: fixed;
  top: 200px; /* genau unter deinem Header (z. B. 80 px hoch) */
  left: 0;
  width: 400px;
  height: calc(100vh - 200px); /* abzüglich der Headerhöhe */
  background-color: white;
  z-index: 800;
  overflow-y: auto;
  padding-left: 60px;
}
</style>
