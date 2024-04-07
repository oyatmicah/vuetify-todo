<template>
  <v-app id="inspire">
    <SideNavigation :drawer="drawer"/>
    <AppBar @toggle-drawer="toggleDrawer"/>
    <!-- <AppBar :drawer="drawer"/> -->

    <v-main>
      <router-view />
    </v-main>
  </v-app>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'

import SideNavigation from '@/components/SideNavigation.vue'
import AppBar from '@/components/AppBar.vue'

export default defineComponent({
  components: {
    SideNavigation,
    AppBar
  },
  setup() {
    const drawer = ref(false)

    const toggleDrawer = () => {
      drawer.value = !drawer.value
    }

    return {
      drawer,
      toggleDrawer,
    }
  },
})
</script>
