<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          v-if="$route.fullPath.includes('/chat')"
          to="/"
          flat
          dense
          icon="arrow_back"
          label="Back"
        />
        <q-toolbar-title class="absolute-center">{{ title }}</q-toolbar-title>
      </q-toolbar>
    </q-header>

    <q-drawer v-model="leftDrawerOpen" show-if-above bordered>
      <q-list>
        <q-item-label header>Essential Links</q-item-label>

        <EssentialLink
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { openURL } from 'quasar';
export default {
  computed: {
    title() {
      let currentPath = this.$route.fullPath;
      if (currentPath == '/') return 'My Chat App';
      else if (currentPath == '/chat') return 'Chat Box';
      else return '404';
    },
  },
  methods: {
    openURL,
  },
};
</script>
