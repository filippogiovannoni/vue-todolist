<script>
export default {
  name: 'App',
  data() {
    return {
      todolist: [
        {
          text: 'Portare fuori il cane',
          done: false
        },
        {
          text: 'Rispondere alle e-mail urgenti',
          done: true
        },
        {
          text: 'Terminare il progetto entro fine settimana',
          done: false
        },
        {
          text: 'Andare a correre per 30 minuti',
          done: true
        },
        {
          text: 'Fare la spesa',
          done: true
        },
        {
          text: 'Pulire la casa',
          done: false
        },
        {
          text: 'Fare rifornimento alla macchina',
          done: false
        },
        {
          text: 'Comprare il biglietto per lo stadio',
          done: true
        },
      ],
      crossed: 'crossed'
    }
  },
  methods: {
    removeTodo(index) {
      console.log('cliccato', index);
      this.todolist.splice(index, 1)
      console.log(this.todolist.length);
    }
  }
}
</script>

<template>
  <div class="container">
    <h1>Todolist</h1>
    <ul v-if="todolist.length > 0">
      <li v-for="(todo, index) in todolist">
        <span v-if="todo.done" :class="crossed">{{ todo.text }}</span>
        <span v-else>{{ todo.text }}</span>
        <div @click="removeTodo(index)">
          <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-x-octagon"
            viewBox="0 0 16 16">
            <path
              d="M4.54.146A.5.5 0 0 1 4.893 0h6.214a.5.5 0 0 1 .353.146l4.394 4.394a.5.5 0 0 1 .146.353v6.214a.5.5 0 0 1-.146.353l-4.394 4.394a.5.5 0 0 1-.353.146H4.893a.5.5 0 0 1-.353-.146L.146 11.46A.5.5 0 0 1 0 11.107V4.893a.5.5 0 0 1 .146-.353zM5.1 1 1 5.1v5.8L5.1 15h5.8l4.1-4.1V5.1L10.9 1z" />
            <path
              d="M4.646 4.646a.5.5 0 0 1 .708 0L8 7.293l2.646-2.647a.5.5 0 0 1 .708.708L8.707 8l2.647 2.646a.5.5 0 0 1-.708.708L8 8.707l-2.646 2.647a.5.5 0 0 1-.708-.708L7.293 8 4.646 5.354a.5.5 0 0 1 0-.708" />
          </svg>
        </div>
      </li>
    </ul>
    <p v-else>Hai completato tutte le cose da fare!🎉</p>
  </div>
</template>

<style></style>
