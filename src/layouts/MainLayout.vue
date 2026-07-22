<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <!-- Navbar title -->
        <q-toolbar-title class="q-ml-lg"> Test App </q-toolbar-title>

        <!-- Navbar buttons -->
        <div
          v-for="headerbutton in headerButtons"
          :key="headerbutton.name" class="q-mx-sm"
        >
          <q-btn
            :label="headerbutton.name"
            flat
            no-caps
          />
        </div>

      </q-toolbar>
    </q-header>

    <q-page-container>
      <router-view />
    </q-page-container>

    <q-footer >
      <q-toolbar>
        <!-- Navbar title -->
        <div>
          <p style="margin: 0px;"> {{ "© Test Seite " + year }} </p>
        </div>

        <div class="col"/>
        <!-- Navbar buttons -->
        <div
          v-for="footerbutton in footerButtons"
          :key="footerbutton.value"
          class="q-mx-sm"
        >
          <router-link
            :to="footerbutton.value"

          >
            {{ footerbutton.name }}
          </router-link>
        </div>
      </q-toolbar>
    </q-footer>
  </q-layout>
</template>

<script setup lang="ts">
import { useQuasar } from 'quasar';

const q = useQuasar();
q.dark.set(true);

const headerButtons = [
  {
    name: "Objekte"
  },
  {
    name: "About me"
  },
  {
    name: "Kontakt"
  },
]

const footerButtons = [
  {
    name: "Datenschutz",
    value: "Noch Route anpassen"
  },
  {
    name: "Impressum",
    value: "Noch Route anpassen bruh"
  },
]

const dateObject = new Date();
const year = dateObject.getFullYear()
</script>
