<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />

        <q-toolbar-title>
          Knjižnica
        </q-toolbar-title>

        <div></div>
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
    >
      <q-list>
        <q-item-label
          header
        >
          Essential Links
        </q-item-label>

        <EssentialLink
          v-for="link in linksList"
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

<script setup>
import { ref } from 'vue'
import EssentialLink from 'components/EssentialLink.vue'

defineOptions({
  name: 'MainLayout'
})

const linksList = [

  {
    title: 'Github',
    caption: 'github.com/knjiznica',
    icon: 'code',
    link: 'https://github.com/etangar/knjiznica.git'
  },
  {
    title: 'Popis knjiga',
    caption: 'popis knjiga',
    icon: 'chat',
    link: '#/popisKnjiga'
  },
  {
    title: 'O nama',
    caption: 'O Nama Page',
    icon: 'record_voice_over',
    link: '#/onama'
  },
  {
    title: 'Lokacija',
    caption: 'Naša Lokacija',
    icon: 'rss_feed',
    link: '#/lokacija'
  },
  {
    title: 'Login',
    caption: 'stranica za login',
    icon: 'public',
    link: '#/login'
  },
  {
    title: 'Registacija',
    caption: 'Registrirajte se',
    icon: 'favorite',
    link: '#/reg'
  },
    {
    title: 'Pretraživanje',
    caption: 'Tražite knjige',
    icon: 'public',
    link: '#/search'
  },
]

const leftDrawerOpen = ref(false)

function toggleLeftDrawer () {
  leftDrawerOpen.value = !leftDrawerOpen.value
}
</script>
