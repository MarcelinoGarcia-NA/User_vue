<template>
  <div class="submitUser" >
      <form id="createUser" @submit="createUser" method="post">
        <p>
          <input
            id="name"
            v-model="name"
            type="text"
            name="name"
            placeholder="Nome"
          >
        </p>
        <p>
          <input
            id="email"
            v-model="email"
            type="text"
            name="email"
            placeholder="Email"
          >
        </p>
        <p>
          <input
            id="password"
            v-model="password"
            type="password"
            name="password"
            placeholder="Password"
          >
        </p>
        <button>Salvar</button>
      </form>
      <ShowMessageVue :msg="message" v-show="message"/>
  </div>
</template>

<script>
import ShowMessageVue from '@/components/ShowMessage.vue';
export default {
  name: 'CadastroUser',
  data(){
    return{
      users:[],
      name:null,
      email:null,
      password:null,
      message:"",
    }
  },
  components: {
    ShowMessageVue
  },
  methods:{
    async createUser(e){
         e.preventDefault();
          const data ={
              name: this.name,
              email: this.email,
              password: this.password,
          }
          const dataJson = JSON.stringify(data);

          const req = await fetch("https://potshop-api.vercel.app/users/",{ 
            method:"POST",
            headers:{"Content-Type":"application/json"},
            body: dataJson
          });

          const res =  await req.json();
          this.message=`Usuario cadastrado com sucesso ${res.name}`;
          console.log(res);
          
          setTimeout(()=>this.message="",5000);
          setTimeout(() => {
            this.$router.push('/');
          },1000);
         
    }  
  },
  mounted(){
      this.getUser();
    }  

}
</script>
<style scoped>
      
      .submitUser{
          width: 30%;
          margin-left:35%;
          border-radius: 1em;
          display: flex;
          justify-content: center;
          align-items: center;
          font-family: 'Montserrat', sans-serif;
          box-shadow:0.1em 0.1em 0.1em 0.1em rgba(0, 0, 0, 0.685);
      }
      .submitUser label{
        color:black;
      }
      .submitUser input {
        height: 30px;
        border-radius: 0.5em;
      }
      .submitUser button{
        width:100px;
        height: 30px;
        margin-left: 20%;
        color: white;
        border-radius: 0.2em;
        background-color: black;
        margin-bottom: 20px;
      }
      .submitUser button:hover{
          cursor: pointer;
      }
        
</style>