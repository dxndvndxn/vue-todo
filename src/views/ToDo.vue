<template>
  <div class="todo">
      <h1>ToDo list</h1>
      <form @submit.prevent="addToDo">
          <label for="addToDo">Add new to do</label>
          <input type="text" id="addToDo" v-model="newDo">
          <button>Add!</button>
      </form>
      <ul>
          <li v-for="(myDo, i) in todoList" :key="i">
              {{++i}} {{myDo.nameToDo}}
          </li>
      </ul>
  </div>
</template>

<script>
export default {
    data: () => ({
        todoList: [],
        newDo: null
    }),
    methods: {
        addToDo(){
            this.todoList.push({nameToDo: this.newDo})
        }
    }
}
</script>

<style>

</style>