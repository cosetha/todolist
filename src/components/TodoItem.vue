<template>
    <div class="list-group">
        <div class="alert alert-success alert-dismissible fade show" role="alert">
            {{title}}
            <button type="button"  class="btn btn-danger float-right mr-1" data-dismiss="alert" aria-label="Close" v-on:click="$emit('remove')">
            <span aria-hidden="true">&times;</span>
            </button>
       <a class="btn btn-primary float-right mr-1" data-toggle="collapse" :href="'#collapseExample'+detail" role="button" aria-expanded="false" aria-controls="collapseExample">
    Detail
  </a>
  

        <div class="collapse" :id="'collapseExample'+detail">
                 <div class="alert alert-success mt-5" role="alert">
        <h5 class="alert-heading">{{matkul}}</h5>
        <p >{{deskripsi}}</p>
        <hr>
        <p class="mb-0">{{deadline}}</p>
        </div>
        </div>
        </div>
        </div>
    
</template>

<script>
export default {
    name:'ToDoItem',
    props:['title','matkul','deadline','deskripsi','detail'],
}
</script>

<style>

</style>