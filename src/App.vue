<template>
  <v-app>
    <Navbar/>
    <v-main>
      <router-view></router-view>
    </v-main>
  </v-app>
</template>

<script>
import HelloWorld from './components/HelloWorld';
import Navbar from './components/Navbar';

export default {
  name: 'App',

  components: {
    HelloWorld,
    Navbar
  },

  data: () => ({
    //
  }),
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;500&display=swap');
.v-application--wrap{
  font-family: 'Poppins', sans-serif;
}
</style>
