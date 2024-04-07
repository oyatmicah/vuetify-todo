<template>
  <v-app-bar>
    <!-- <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon> -->
    <v-app-bar-nav-icon @click="toggleDrawer"></v-app-bar-nav-icon>
    <v-app-bar-title>Todo List Application </v-app-bar-title>
  </v-app-bar>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  setup(props, { emit }) {
    const toggleDrawer = () => {
      emit('toggle-drawer')
    }

    return {
      toggleDrawer,
    }
  },
})
</script>
