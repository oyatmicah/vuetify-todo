<template>
  <v-app id="inspire">
    <v-navigation-drawer image="https://cdn.vuetifyjs.com/images/backgrounds/bg-2.jpg" theme="dark" permanent
      v-model="drawer">
      <v-list nav>
        <v-list-item to="/" prepend-icon="mdi-format-list-checks" title="Todo" value="todos"></v-list-item>
        <v-list-item to="/about" prepend-icon="mdi-help-box" title="About" value="about"></v-list-item>
      </v-list>
    </v-navigation-drawer>
    <!-- <SideNavigation /> -->

    <v-app-bar>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

      <v-app-bar-title>Todo List Application </v-app-bar-title>
    </v-app-bar>

    <v-main>
      <router-view />
    </v-main>
  </v-app>
</template>

<script lang="ts">
import { defineComponent, ref, Ref } from 'vue'

export default defineComponent({
  setup() {
    const drawer: Ref<null> = ref(null)

    return {
      drawer,
    }
  },
})
</script>

