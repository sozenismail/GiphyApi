<template>

  <div class="container-fluid">
  <div class="row">
        
        <ul>
       
        <li v-for="gif in gifs">
              

             <div class="col-12">
             
                 <img :src="gif.images.fixed_height.url" />
             </div>
               
         </li>
       
        </ul>
  
     </div>
  </div>
</template>

<script>
    export default {
        props: ['gifs']

    }
</script>

<style>
 

li{
    list-style:none;
    float:left;
    margin:25px;

}

</style>