<script>
export default {
  name: 'App',

  data() {
    return {

      toDoList: [
        {
          text: 'Pranzo amici',
          done: false,
          x: 'fa-regular fa-circle-xmark',
          check: 'check-style',
        },
        {
          text: 'Reunione con clienti',
          done: false,
          x: 'fa-regular fa-circle-xmark',
          check: 'check-style',
        },
        {
          text: 'Compito di martedí',
          done: false,
          x: 'fa-regular fa-circle-xmark',
          check: 'check-style',
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
        <li class="itemList">
          <input type="checkbox" @change="toDoList[0].done = true" :class="toDoList[0].check">
          <p :class="toDoList[0].done === true ? 'sbarra' : 'nonSbarra'">
            {{ toDoList[0].text }}</p>
          <i :class="toDoList[0].x" @click="toDoList[0].text = '', toDoList[0].x = ' ', toDoList[0].check = 'd-non'"></i>
        </li>


        <li class="itemList">
          <input type="checkbox" @change="toDoList[1].done = true" :class="toDoList[1].check">
          <p :class="toDoList[1].done === true ? 'sbarra' : 'nonSbarra'">
            {{ toDoList[1].text }}</p>
          <i :class="toDoList[1].x" @click="toDoList[1].text = '', toDoList[1].x = ' ', toDoList[1].check = 'd-non'"></i>
        </li>


        <li class="itemList">
          <input type="checkbox" @change="toDoList[2].done = true" :class="toDoList[2].check">
          <p :class="toDoList[2].done === true ? 'sbarra' : 'nonSbarra'">
            {{ toDoList[2].text }}</p>

          <i :class="toDoList[2].x" @click="toDoList[2].text = '', toDoList[2].x = ' ', toDoList[2].check = 'd-non'"></i>
        </li>


      </ul>
    </div>
  </main>

  <footer>
    <p>Footer</p>
  </footer>
</template>

<style></style>
