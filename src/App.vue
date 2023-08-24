<template>
  <div id="app">

 <h1>Fazer cadastro</h1>

 <div>

    <form  @submit.prevent="enviar">
      <label>Nome: </label>
      <input type="text" v-model="user.nome"><br/>

   <label>Email: </label>
     <input type="email" v-model="user.email"/><br/>

     <label>Qtd Funcionarios: </label>
      <input type="number" v-model="user.qtdfunc">

     <label>Opinião: </label>
    <textarea v-model="opinião"></textarea>

    <label>Tecnologia </label>
    <span>

   <input type="checkbox" value="javascript" v-model="tecnologia"/> javascript
   <input type="checkbox" value="css" v-model="tecnologia"/> css
   <input type="checkbox" value="html" v-model="tecnologia"/>Html


    </span><br>

<label>Qual o tipo de contratação </label>

<select v-model="tipoSelecionado">
 
 <option v-for="item in tipos" :key="item.id" :value="item.nome">{{item.nome}}</option>
 
</select><br>

<button type="submit">Enviar</button>

  </form>
 </div>

 <hr>

<div class="item" v-show="resultado">

<h2>Usuario cadastrado</h2>

<label>Nome: {{user.nome}}</label> <br>
<label>Email: {{user.email}}</label> <br>

<label>Qtd Funcionarios: {{user.qtdfunc}}</label> <br>

<label>Sua Opinião: {{opinião}}</label><br>

<label>Tecnologia: {{tecnologia}}</label> <br>

<label>Tecnologia:</label>
<ul>
  <li v-for="tech in tecnologia" :key="tech">{{tech}}</li>
</ul>
</div>

  <label>Tipo de Contratação: {{tipoSelecionado}}</label>

  </div>
  

</template>

<script>
//import Usuario from './Components/Usuario';

  export default{
    name: 'App',
    data(){
      return{
        //nome:'',
        //email:'',
      //qtdfunc:'0',
/////Posso ter um objeto com todo do formulario exe;
        user:{
          nome:'',
        email:'',
      qtdfunc:'0',

        },
        opinião:'',
        //tem que colocar como array 
        tecnologia:[],
        tipos:[
          {id:1,nome:'Freelancer'},
         {id:2,nome:'CLT'},
         {id:3,nome:'PJ'},
        
        ],
        tipoSelecionado: 'freelancer'
      }
    },resultado:false,
    methods:{
      enviar(){
        this.resultado = true
       
      }
    }

    
  }
</script>

<style>

form{
    
  display: flex;
  flex-direction: column; 

}

</style>