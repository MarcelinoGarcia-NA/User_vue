<template>
    <div class="ShowMessage">
        <h1>{{ msg }}</h1>
    </div>
</template>
<script>
    export default{
        name:'ShowMessage',
    data(){
        return{
            
        }
    },
    props:{
        msg:String
  },
}
</script>
<style scoped>
    .ShowMessage{
        width:auto;
        max-width: 300px;
        height: 40px;
        margin-top:50px;
        border-top: 50px;
        background-color: rgb(117, 169, 236);
        border: 0.1em rgb(4, 88, 88) solid;
        border-radius:10px;
    }
    .ShowMessage h1{
        padding:0px;
        color:white;
        margin:0px;
        text-align:center;
    }
</style>