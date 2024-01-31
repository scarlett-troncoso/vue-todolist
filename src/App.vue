<script>
export default {
  name: 'App',

  data() {
    return {

      newText: {
        text: '',
        done: false,
      },

      toDoList: [
        {
          text: 'Pranzo amici',
          done: false,
        },
        {
          text: 'Reunione con clienti',
          done: true,
        },
        {
          text: 'Compito di martedí',
          done: true,
        },
        {
          text: 'Colloquio',
          done: true,
        },
      ]
    }
  },

  methods: {
    removeItem(index) {
      console.log('rimovere questo item', index);
      this.toDoList.splice(index, 1);
    },

    addTask() {
      console.log('Aggiunge task:', this.newText.text);
      const newObject = { ...this.newText } //i tre puntini aggiungono il contenuto del newText
      this.toDoList.unshift(newObject);//nell array si aggiunge newObject perche newText ancora si deve sempre riempire di nuovo
      this.newText.text = '';
    }
  }
}
</script>

<template>
  <header>
    <h1 class="m-3">To Do List</h1>
  </header>

  <main>
    <div class="card w-50 m-auto">
      <div class="input-group mt-3 align-items-center justify-content-center">
        <button for="addTask" class="btn btn-secondary" @click="addTask">Add task</button>
        <input type="text" id="addTask" v-model="newText.text">
      </div>

      <ul v-if="toDoList.length > 0" class="ul-list">

        <li v-for="(item, index) in  toDoList" class="itemList" :class="{ sbarra: item.done }">

          <!--<input type="checkbox" v-on:click="item.done = true">-->

          <!--<p :class="item.done ? 'sbarra' : ''"> --> <!--potrebbe essere anche cosí come ho fatto prima-->
          <!--mette la class in item.done sólo in quelli che sono true-->
          {{ item.text }}

          <span v-on:click="removeItem(index)">
            <i class="fa-regular fa-circle-xmark m-1"></i>
          </span>
        </li>
      </ul>

      <p v-else class="ul-list">
        No task to do
      </p>
    </div>
  </main>
</template>

<style></style>
