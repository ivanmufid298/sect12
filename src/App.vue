<template>
  <div id="app">
        <ol>
            <li v-for="todo in list" :key="todo.id">
              {{ todo }} &nbsp;
            </li>
          </ol>
      <p>
        <input type="text" v-model="inputTodo" />
        <button @click="create">Tambahkan</button>
      </p>
      <p v-if="list.length >= 4" > Hebat </p>
    </div>
</template>

<script>
export default {
  name: 'App', 
  data(){
    return{
      list: [],
      inputTodo: ""
    };
  },
  methods: {
    create(){
      if (this.inputTodo != ""){
        this.list.push(this.inputTodo);
        this.inputTodo = "";
      }
    }
  },
}
</script>
