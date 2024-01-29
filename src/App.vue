<script>
export default {
  name: 'App',

  data() {
    return {

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
      ]
    }
  },

  methods: {
    removeItem(index) {
      console.log('rimovere questo item', index);
      this.toDoList.splice(index, 1);
    }
  }
}
</script>

<template>
  <header>
    <h1>To Do List</h1>
  </header>

  <main>
    <ul v-if="toDoList.length > 0">
      <li v-for="(item, index) in toDoList" class="itemList">
        <!--<input type="checkbox" @change="item.done = true">-->
        <p :class="item.done ? 'sbarra' : ''">
          {{ item.text }}

          <span v-on:click="removeItem(index)">
            <i class="fa-regular fa-circle-xmark"></i>
          </span>
        </p>

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
