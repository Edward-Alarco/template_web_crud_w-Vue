<template>
  <div class="home">
    <Banner/>
    <Servicios/>
    <Form/>
    <Footer/>
  </div>
</template>

<script>
// @ is an alias to /src
import Banner from '@/components/Banner.vue'
import Servicios from '@/components/Servicios.vue'
import Form from '@/components/Form.vue'
import Footer from '@/components/Footer.vue'

export default {
  
  name: 'Home',
  components: {
    Banner, Servicios, Form, Footer
  }
}
</script>

<style>
.home{
  background-color: #333;
}
</style>
