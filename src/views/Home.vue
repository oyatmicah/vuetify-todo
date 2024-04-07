<template>
  <div class="home pa-6">
    <h1>Todo</h1>

    <v-text-field
      v-model="newTaskTitle"
      @click:append="addTask"
      @keyup.enter="addTask"
      class="pa-3"
      append-icon="mdi-plus"
      label="Add task"
      variant="underlined"
      hide-details
      clearable
    ></v-text-field>

    <v-list class="pt-0" lines="three" select-strategy="classic">

      <div v-for="task in tasks" :key="task.id">
        <v-list-item @click="doneTask(task.id)" :class="{ 'blue lighten-5': task.done }">
          <template v-slot:prepend>

            <v-list-item-action start>
              <v-checkbox-btn :model-value="task.done"></v-checkbox-btn>
            </v-list-item-action>
          </template>

          <v-list-item-title :class="{'text-decoration-line-through' : task.done}">{{ task.title }}</v-list-item-title>

          <template v-slot:append>
            <v-btn
            @click.stop="deleteTask(task.id)"
              color="primary"
              icon="mdi-delete"
              variant="text"
            ></v-btn>
          </template>
        </v-list-item>
        <v-divider></v-divider>
      </div>

    </v-list>
  </div>
</template>

<script lang="ts">

export default {
  data() {
    return {
      newTaskTitle: '',
      tasks: []
    }
  },
  methods: {
    addTask(){
      let newTask = {
        id: Date.now(),
        title: this.newTaskTitle,
        done: false
      }
      this.tasks.push(newTask)
      this.newTaskTitle = ''
    },
    doneTask(id) {
      let task = this.tasks.filter(task => task.id === id)[0]
      task.done = !task.done
    },
    deleteTask(id) {
       this.tasks = this.tasks.filter(task => task.id !== id)
    }
  }
}
</script>
