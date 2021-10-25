<template>
    <div>
          <v-toolbar color="purple" app>

              <v-toolbar-side-icon>
                 <v-btn icon @click="drawer = !drawer">
                      <v-icon>menu</v-icon>
                 </v-btn>
              </v-toolbar-side-icon>
              
              <v-toolbar-title> Producto </v-toolbar-title>

               <v-spacer></v-spacer>

               <v-btn style="margin-right:5px" class="success" elevation="2" small>
                   Entry
               </v-btn>
               
               <v-btn class="error" elevation="2" small>
                   Logout
               </v-btn>

          </v-toolbar>    

      <v-navigation-drawer app v-model="drawer" temporary>
         
          <v-layout mt-4 column align-center>

              <v-flex>

                  <v-avatar>
                      <v-img src="https://randomuser.me/api/portraits/women/85.jpg"></v-img>
                  </v-avatar>

              </v-flex>
              <v-flex>
                  <p class="white--text mt-3 headline">Nombre usuario</p>
              </v-flex>

          </v-layout>

          <v-layout>

              <v-list
                    nav
                    dense
              >
        <v-list-item-group
          v-model="group"
          active-class="deep-purple--text text--accent-4"
        >
          <v-list-item>
            <v-list-item-title @click="cambiarComponent('create')">Nuevo producto</v-list-item-title>
          </v-list-item>

          <v-list-item>
            <v-list-item-title @click="cambiarComponent('list')">Lista producto</v-list-item-title>
          </v-list-item>

          <v-list-item>
            <v-list-item-title>Item</v-list-item-title>
          </v-list-item>

          <v-list-item>
            <v-list-item-title>Item</v-list-item-title>
          </v-list-item>
        </v-list-item-group>
      </v-list>

          </v-layout>

      </v-navigation-drawer>
     
   
     <component v-bind:is="actual"></component>
    
      

    </div>
</template>

<script>
import create from './create.vue';
import List from './list.vue';

export default {
  components: { create, List,},
 
name : 'inicio',
data() {
    return {
       drawer: true,
       actual: 'create'
    };
},

methods: {
  cambiarComponent(component) {
    this.actual = component;
  },
},

}
</script>