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
          x: 'fa-regular fa-circle-xmark',
        },
        {
          text: 'Reunione con clienti',
          done: true,
          x: 'fa-regular fa-circle-xmark',
        },
        {
          text: 'Compito di martedí',
          done: false,
          x: 'fa-regular fa-circle-xmark',
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
        <li v-for="toDo in toDoList" :class="toDo.done === true ? 'sbarra' : 'nonSbarra'" id="itemList" class="itemList">
          {{ toDo.text }}
          <i :class="toDo.x" @click="toDo.text = '', toDo.x = ' '"></i>
        </li>


      </ul>
    </div>
  </main>

  <footer>
    <p>Footer</p>
  </footer>
</template>

<style></style>
