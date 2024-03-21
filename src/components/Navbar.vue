<template>
    <div class="nav">
        <a href="#" class="logo">SUSB</a>
        <div class="links">
            <router-link to="/">Home</router-link>
            <router-link to="/sobre">Sobre</router-link>
        </div>
    </div>
</template>

<script>

export default{
    nome: 'Navbar'
}
</script>

<style scoped>
.nav{
    background: linear-gradient( #fbff00, #00e1ff);
    padding: 15px 50px;
    display: flex;
    justify-content: flex-end;
    align-items: center;
}
.logo{
    font-size: 32px;
    color: blue;
    text-decoration: none;
    font-weight: 700;
    margin: auto;
    margin-left: 0;
    font-family:'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
}
.links a{
    font-family: Arial;
    font-size: 18px;
    color: #fff;
    text-decoration: none;
    font-weight: 500;
    margin-left: 20px;
    transition: .5s;
}
.links a:hover{
    color: rgb(36, 208, 251);
}
@media only screen and (max-widht: 600px){

}
</style>