<template>
  <v-navigation-drawer image="https://cdn.vuetifyjs.com/images/backgrounds/bg-2.jpg" theme="dark" permanent
    v-model="drawer">
    <v-list nav>
      <v-list-item to="/" prepend-icon="mdi-format-list-checks" title="Todo" value="todos"></v-list-item>
      <v-list-item to="/about" prepend-icon="mdi-help-box" title="About" value="about"></v-list-item>
    </v-list>
  </v-navigation-drawer>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  props: {
    drawer: Boolean,
  },
})
</script>
