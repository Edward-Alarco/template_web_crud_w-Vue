<template>
  <div class="home">
    <Banner/>
    <Servicios/>
    <Form/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import Banner from '@/components/Banner.vue'
import Servicios from '@/components/Servicios.vue'
import Form from '@/components/Form.vue'

export default {
  
  name: 'Home',
  components: {
    HelloWorld, Banner, Servicios, Form
  }
}
</script>

<style>
.home{
  background-color: #333;
}
</style>
