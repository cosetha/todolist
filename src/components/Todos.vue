<template>
  <div class="row">
    <div class="col-md-4">
      <form v-on:submit.prevent="addTodo">
        <div class="form-group">
          <label for="nama">Nama Tugas</label>
          <input v-model="tugas" class="form-control" id="nama">
        </div>
        <div class="form-group">
          <label for="matkul">Mata Kuliah</label>
          <input v-model="matkul" class="form-control" id="matkul">
        </div>
        <div class="form-group">
          <label for="deadline">Deadline</label>
          <input v-model="deadline" type="date" class="form-control" id="deadline">
        </div>
         <div class="form-group">
          <label for="deskripsi">Deskripsi</label>
          <textarea v-model="deskripsi" type="date" class="form-control" row ="6" id="deskripsi"/>
        </div>
        <button class="btn btn-info">Add To Do</button>
        <hr>
      </form>
    </div>
    <div class="col-md-8">
      <ul>
        <TodoItem
          v-for="(todo, index) in todos"
          v-bind:key="index"
          v-bind:title="todo.namaTugas"
          v-bind:detail="index"
          v-bind:matkul="todo.mataKuliah"
          v-bind:deadline="todo.deadlineTugas"
          v-bind:deskripsi="todo.deskripsiTugas"
          v-on:remove="todos.splice(index, 1)"
        ></TodoItem>
      </ul>
    </div>
  </div>
</template>

<script>
import TodoItem from '../components/TodoItem.vue'
export default {
  name: 'Todos',
  props: {
    
  },
  components:{
    TodoItem
  },
  data(){
    return{
      todos: [],
      tugas:"",
      matkul:"",
      deadline:"",
      deskripsi:"",
    }
  },
  methods:{
    addTodo: function(){
      this.todos.push({
        namaTugas:this.tugas,
        mataKuliah:this.matkul,
        deadlineTugas:this.deadline,
        deskripsiTugas:this.deskripsi
      })
      this.tugas="",
      this.matkul="",
      this.deadline="",
      this.deskripsi=""
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
textarea { resize:none; }
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
