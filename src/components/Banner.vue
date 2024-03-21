<template>
    <div class="cont">
        <img src="../assets/Img/banner.jpg" width="350" alt="banner">
       <h1>O que somos</h1>
       <p>
          A SUSB (Saúde Universal e Sustentável do Brasil) surgiu como uma resposta às crescentes necessidades de cuidados de saúde de qualidade para todos os brasileiros. 
          Sua jornada começou com um grupo de visionários dedicados à missão de fornecer acesso equitativo a serviços de saúde de alta qualidade, independentemente da condição socioeconômica.
       </p>
    </div>
</template>

<script>
export default{
    name: 'Banner'
}
</script>

<style scoped>
.cont{
    overflow: auto;
}
.cont img{
  float: left;
  margin-right: 20px;
}
h1{
    text-align: center;
    color: cornflowerblue;
}
p{
    margin-top: 50px;
    font-size: 20px;
    color:lightseagreen ;
}
@media only screen and (max-width: 700px){
    img{
        width: 270px;
    }
}
</style>