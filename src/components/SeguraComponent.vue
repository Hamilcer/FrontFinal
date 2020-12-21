<template>
  <v-app id="inspire">
      <v-card>
        <v-navigation-drawer
          permanent
          expand-on-hover
        >
          <v-list class="pt-6" >
            <v-list-item link>
              <v-list-item-content>
                <v-list-item-title class="title">
                  {{ this.$store.state.user.nombre }}
                </v-list-item-title>
                <v-list-item-subtitle> {{this.$store.state.user.email}} </v-list-item-subtitle>
              </v-list-item-content>
            </v-list-item>
          </v-list>
  
          <v-divider></v-divider>
  
          <v-list
            nav
            dense
          >
            <v-list-item link :to="{ name: 'Home' }">
              <v-list-item-icon>
                <v-icon>mdi-home</v-icon>
              </v-list-item-icon>
              <v-list-item-title>Home</v-list-item-title>
            </v-list-item>
            
            <v-list-item link :to="{ name: 'Categoria' }">
              <v-list-item-icon>
                <v-icon>mdi-clipboard-list</v-icon>
              </v-list-item-icon>
              <v-list-item-title>Categorias</v-list-item-title>
            </v-list-item>

            <v-list-item link :to="{ name: 'Articulo' }">
              <v-list-item-icon>
                <v-icon>mdi-clipboard-list-outline</v-icon>
              </v-list-item-icon>
              <v-list-item-title>Articulos</v-list-item-title>
            </v-list-item>

            <v-list-item link :to="{ name: 'Usuario' }">
              <v-list-item-icon>
                <v-icon>mdi-account-multiple</v-icon>
              </v-list-item-icon>
              <v-list-item-title>Usuarios</v-list-item-title>
            </v-list-item>

          </v-list>
          <v-spacer></v-spacer>
          <template v-slot:append>
          <v-list-item >
              <v-list-item-icon>
                <v-icon>mdi-logout</v-icon>
              </v-list-item-icon>
              <v-list-item-title>
              <v-btn block >
                Logout
              </v-btn>
              </v-list-item-title>
          </v-list-item>
          </template>


        </v-navigation-drawer>
      </v-card>
  </v-app>

</template>

<script>
export default {
  name: "SeguraComponent",

  components: {},

  data: () => ({
    //
    drawer: null,
  }),
  created() {
    this.$store.dispatch("autoLogin");
  },
  methods: {
    salir() {
      this.$store.dispatch("salir");
    },
  },
};
</script>

<style scoped>
  .v-card{
    height: 100vh;
  }

</style>
