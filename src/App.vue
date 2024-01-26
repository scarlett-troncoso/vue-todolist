<script>
export default {
  name: 'App',

  data() {
    return {
      /*toDoList: {
        text: ['Pranzo amici', 'Reunione con clienti', 'Compito di martedí'],
        done: true,
      }*/

      toDoList: [
        {
          text: 'Pranzo amici',
          done: true,
        },
        {
          text: 'Reunione con clienti',
          done: true,
        },
        {
          text: 'Compito di martedí',
          done: false,
        },
      ]
    }
  },

}


</script>

<template>
  <header>
    <h1>To Do List</h1>
  </header>

  <main>
    <div>
      <ul>
        <li v-for="toDo in toDoList" :class="toDo.done === true ? 'sbarra' : 'nonSbarra'">
          {{ toDo.text }}
        </li>

      </ul>
    </div>
  </main>

  <footer>
    <p>Footer</p>
  </footer>
</template>

<style></style>
