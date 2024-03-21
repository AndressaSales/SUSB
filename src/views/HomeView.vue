<template>
    <div class="container">
      <Banner/>
      <h1>Formulário</h1>
      <Formulario/>
    </div>
</template>

<script>
import Banner from '@/components/Banner.vue';
import Formulario from '../components/Formulario.vue';

export default{
  name: 'Home',
  components:{
    Banner,
    Formulario
  }
}
</script>

<style scoped>
.container h1{
  text-align: center;
  margin-top: 20px;
  color: cornflowerblue;
  margin-bottom: 30px;
}
</style>