<script>
export default {
  name: 'App',

  data() {
    return {
      newTask: '',

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
      //const { text, done } = toDoList;
      console.log('Aggiunge task:', this.newTask);

      //this.toDoList.map(item => item.text.push(this.newTask));
      this.toDoList.unshift(this.newTask);
      this.newTask = '';
    }
  }
}
</script>

<template>
  <header>
    <h1>To Do List</h1>
  </header>

  <main>

    <div class="m-1">
      <label for="addTask" class="m-1" @click="addTask">Add task</label>
      <input type="text" id="addTask" v-model="newTask">
    </div>

    <ul v-if="toDoList.length > 0">
      <li v-for="(item, index) in  toDoList" class="itemList" :class="{ sbarra: item.done }">
        <!--<input type="checkbox" @change="item.done = true">-->
        <!--<p :class="item.done ? 'sbarra' : ''"> --> <!--potrebbe essere anche cosí come ho fatto prima-->
        <!--mette la class in item.done sólo in quelli che sono true-->
        {{ item.text }}

        <span v-on:click="removeItem(index)">
          <i class="fa-regular fa-circle-xmark m-1"></i>
        </span>
      </li>
    </ul>

    <p v-else>
      No task to do
    </p>
  </main>

  <footer>
    <p>Footer</p>
  </footer>
</template>

<style></style>
