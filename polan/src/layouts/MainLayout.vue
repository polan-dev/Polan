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
          polan
        </q-toolbar-title>

        <div>Quasar v{{ $q.version }}</div>
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
          Navigation
        </q-item-label>

        <q-item
        to="/main"
        exact
    clickable
   
  >
    <q-item-section
      avatar
    >
      <q-icon name="home" />
    </q-item-section>

    <q-item-section>
      <q-item-label>main</q-item-label>
      
    </q-item-section>
  </q-item>
  <q-item
        to="/settings"
        exact
    clickable
   
  >
    <q-item-section
      avatar
    >
      <q-icon name="settings" />
    </q-item-section>

    <q-item-section>
      <q-item-label>settings</q-item-label>
      
    </q-item-section>
  </q-item>
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>


import { defineComponent, ref } from 'vue'

export default defineComponent({
  name: 'MainLayout',

 
  setup () {
    const leftDrawerOpen = ref(false)

    return {
      
      leftDrawerOpen,
      toggleLeftDrawer () {
        leftDrawerOpen.value = !leftDrawerOpen.value
      }
    }
  }
})
</script>
