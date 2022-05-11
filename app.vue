<template>
  <v-app theme="dark">
    <v-navigation-drawer app :rail="drawer">
      <v-list nav color="transparent">
        <v-list-item prepend-icon="mdi-view-dashboard" title="Dashboard"></v-list-item>
        <v-list-item prepend-icon="mdi-account-box" title="Account"></v-list-item>
        <v-list-item prepend-icon="mdi-gavel" title="Admin"></v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar app>
      <template v-slot:prepend>
        <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
      </template>
      <v-app-bar-title>{{ title }}</v-app-bar-title>
    </v-app-bar>
    <v-main>
      <v-container fluid>
        <nuxt-page></nuxt-page>
      </v-container>
    </v-main>
    <v-footer
        app
    >
      <v-row
          justify="center"
          no-gutters
      >
        <v-btn
            v-for="link in links"
            :key="link"
            variant="text"
            class="mx-2"
            rounded="xl"
        >
          {{ link }}
        </v-btn>
        <v-col
            class="text-center text-white mt-4"
            cols="12"
        >
          {{ new Date().getFullYear() }} — <strong>Vuetify</strong>
        </v-col>
      </v-row>
    </v-footer>
  </v-app>
</template>

<script setup>
import { ref } from 'vue'

const drawer = ref(false)

const title = 'My Recent Trips'
const links = ['Home',
  'About Us',
  'Team',
  'Services',
  'Blog',
  'Contact Us']
</script>
