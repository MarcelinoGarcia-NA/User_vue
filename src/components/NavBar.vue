<template>
    <nav class="NavBar">
      <router-link to="/" class="nav-link">Home</router-link> 
      <router-link to="/cadastro" class="nav-link">Cadastro</router-link>
      <router-view/>
    </nav>
</template>
<script>
export default {
    name:'NavigationBar',
    data() {
        return{

        }
    },
}
</script>
<style scoped>
    .NavBar{
        width: 100%;
        height: 100px;
        color:white;
        font-family: 'Montserrat', sans-serif;
        background-color: black;
    }
    .nav-link{
        width: 50px;
        height: 100px;
        padding: 35px;
        max-width: 70px;
        font-style: oblique;
        color:white;
        font-size: 20px;
        display: inline-block;
        justify-content: left;
        text-decoration: none;
    }
</style>