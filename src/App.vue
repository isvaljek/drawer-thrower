<template>
  <v-app>
    <v-app-bar
      app
      color="primary"
      dark
    >      
      <div class="d-flex align-center">
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
          transition="scale-transition"
          width="40"
        />

        <v-img
          alt="Vuetify Name"
          class="shrink mt-1 hidden-sm-and-down"
          contain
          min-width="100"
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-name-dark.png"
          width="100"
        />
      </div>

      <v-spacer></v-spacer>

      <v-app-bar-nav-icon @click.stop="showDrawer = !showDrawer"></v-app-bar-nav-icon>
      
    </v-app-bar>

    <v-main>
      <v-navigation-drawer v-model="showDrawer" absolute>
        <v-checkbox v-for="(item, i) in checkboxes" :key="i" label="Clicker"></v-checkbox>
        <br />
      </v-navigation-drawer>
      <HelloWorld/>
      <Lipsum v-for="(item, i) in lipsums" :key="i" />
    </v-main>
  </v-app>
</template>

<script>
import HelloWorld from './components/HelloWorld';
import Lipsum from './components/Lipsum';

export default {
  name: 'App',

  components: {
    HelloWorld,
    Lipsum
  },

  computed: {
    json_kozmo() {
      return this.kozmo
    }
  },

  async mounted() {
    
    
  },

  data: () => ({
    checkboxes: Array(100),
    lipsums: Array(5),
    showDrawer: false,
  }),
};
</script>
