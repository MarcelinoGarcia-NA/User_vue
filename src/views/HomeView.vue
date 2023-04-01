<template>
  <div>
      <table class="home">
          <tr>
            <th style="padding: 1.5em; padding-bottom: 0.5em;">
                NOME
                <hr>
            </th>
            
            <th style="padding: 1.5em; padding-bottom: 0.5em;">
                E-MAIL
                <hr>
            </th>
          </tr>
          <tr v-for="user in users" :key="user.id">
            <th>
              <td>{{ user.name.toUpperCase() }}</td>
            </th>
            <th>
              <td>{{ user.email }}</td>
            </th>
          </tr>
      </table>
      </div>
</template>

<script>

export default {
  name: 'HomeView',
  data(){
    return{
      users:[]
    }
  },
  components: {
   
  },
  methods:{
    async getUser(){
        const res = await fetch("https://potshop-api.vercel.app/users");
        const data = await res.json();
         console.log(data);
         this.users= data;     
    },
  },
  mounted(){
      this.getUser();
    } 


}
</script>
<style scoped>
.home{
  width:80%;
  margin: 0 auto;
  height: 50%;
  color:black;
  border-radius: 1em;
  font-family: 'Montserrat', sans-serif;
  box-shadow:0.1em 0.1em 0.1em 0.1em rgba(0, 0, 0, 0.685);
}
.home th{
  padding-left: 1em;
  text-align: left;
}
.home th td{
   padding:0.8em;
   font-weight: 600;
}
</style>
