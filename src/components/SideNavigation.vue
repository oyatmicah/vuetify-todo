<template>
  <v-navigation-drawer image="https://cdn.vuetifyjs.com/images/backgrounds/bg-2.jpg" theme="dark" permanent
      v-model="drawer">
      <v-list nav>
        <v-list-item prepend-icon="mdi-view-dashboard" title="Todo" value="todos"></v-list-item>
        <v-list-item prepend-icon="mdi-help-box" title="About" value="about"></v-list-item>
      </v-list>
    </v-navigation-drawer>
</template>

<script setup>
import { ref } from 'vue'

const drawer = ref(null)
</script>

<script>
export default {
  data: () => ({ drawer: null }),
}
</script>
