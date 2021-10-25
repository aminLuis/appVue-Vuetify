<template>
  <v-app id="app">
    
    <v-main>
  
  <!-- Here add components -->
     <inicio/>
    </v-main>
   
  </v-app>
</template>

<script>
import Inicio from './components/articulo/inicio.vue';


export default {
  name: 'App',

  components: {
   Inicio,
  },
    

  data: () => ({
    //
  }),
};
</script>
