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
  }
}
</script>

<template>
  <div class="container">
    <h1>Todolist</h1>
    <ul>
      <li v-for="todo in todolist">
        <span v-if="todo.done === true" :class="crossed">{{ todo.text }}</span>
        <span v-else>{{ todo.text }}</span>
      </li>
    </ul>
  </div>
</template>

<style></style>
