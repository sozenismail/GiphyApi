<template>

<div class="container">
 

    <div class="row">

    <div class="col-md-8">
    <input type="text" v-on:keyup.enter="handleSearch" v-model="query" class="form-control"  placeholder="Search all the GIFs"/>
    </div>
    <div class="col-md-1">
    <button @click="handleSearch" class="btn btn-success">Search</button>
    </div>
     
</div>

</div>
</template>


<script>

 
 
 export default {
      
      data() {
          return {
              query: ''
          }
      },
      methods: {
          handleSearch() {
              
              this.$emit('SearchRequested',this.query);
              
              
          }
      },

 }

</script>

<style>

 

 

</style>