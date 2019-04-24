<template>
  <div id="app">

    <search v-on:SearchRequested="handleSearch"></search>
    <preview :gifs=gifs></preview>
  </div>
</template>


<script>


import  Search  from "./components/search.vue";
import  Preview  from "./components/preview.vue";
export default {
  name: 'app',
  data() {
    return {
      gifs: []
    }
  },

   methods: {
   handleSearch(query) {

    

       this.gifs= [];


    fetch(`http://api.giphy.com/v1/gifs/search?q=${query}&api_key=nWbUb6o43ZCyZ62o0UWkJER07YyZpaiy`)
   .then((res) => {return res.json() } )
   .then((res) => { this.gifs=res.data; })  
     
     if (query =='') {

        fetch('http://api.giphy.com/v1/gifs/trending?api_key=nWbUb6o43ZCyZ62o0UWkJER07YyZpaiy')
   .then((res) => {return res.json() } )
   .then((res) => { this.gifs=res.data; })   
       
     }
     
   }
 },

  components: {Search,Preview},
 created () {
     fetch('http://api.giphy.com/v1/gifs/trending?api_key=nWbUb6o43ZCyZ62o0UWkJER07YyZpaiy')
   .then((res) => {return res.json() } )
   .then((res) => { this.gifs=res.data; })   


 }

}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
 
</style>
