<template>
  <div id="app"> 
    <Menu/>
     <h1>Cadastro</h1>
        <div id="form">
         <div id="info">
             <label for="Nome">Nome</label>
             <input type="text"  class="input" v-model="nomeField">

             <label for="email">Email</label>
             <input type="text"  class="input" v-model="emailField">

             <label for="cpf">CPF</label>
             <input type="text"  class="input" v-model="cpfField">
         </div> 
         <div id="end">
         <div class="colun1">
             <label for="endereço">Endereço</label>
             <input type="text"  class="inputend" v-model="endereçoField"> 

             <label for="estado">Estado</label>
             <input type="text"  class="inputend" v-model="estadoField"> 
         </div>
         <div class="colun2">
             <label for="cep">CEP</label>
             <input type="text" class="inputend" v-model="cepField"> 

             <label for="cidade">Cidade</label>
             <input type="text"  class="inputend" v-model="cidadeField"> 
         </div> 
           </div>
        </div>
        <h1>  Forma de Pagamento </h1>  
         <div id="pagamento">  
            <label for="male">
                <input type="radio" id="male" :value="Male" v-model="radioBoxOption"> Cartao de Credito
           </label>
           <label for="female"> <input type="radio"  id="female" :value="Female" v-model="radioBoxOption"> Boleto Bancario
           </label>
           <div id="end">
         <div class="colun1">
             <label for="nomeC">Nome no Cartão</label>
             <input type="text"  class="inputC" v-model="nomeCField"> 

             <label for="numeroC">Número da Cartão</label>
             <input type="number"  class="inputC" v-model="numeroCField"> 
         </div>
         <div class="colun2">
             <label for="dataE">Data de Expiração</label>
             <input type="number"  class="inputC" v-model="dataEField"> 

             <label for="password">Código de Segurança</label>
             <input type="password" class="inputC" v-model="passwordField">    
         </div>  
        </div>
           
            </div> 
          <h4>Seu cartão será debitado em R$ 49,00</h4>
            <button @click="salvar"> REALIZAR MATRÍCULA</button>
            <div>
                
            </div>
   
                <h1>Listas</h1>
      <table id="listaT">
        <thead>
            <tr class="tabela">
                <th> Nome</th>
                <th> Email</th>
                <th> CPF</th>
                <th> CEP</th>
                </tr>
        </thead>     
     </table>

         <div v-for="cliente in clientes" :key="cliente.id">
           
            <Cadastro :cliente="cliente" />
        </div>
    <Footer/>
  
  </div>

</template>

<script>


import Menu from './components/Menu.vue'
import Cadastro from './components/Cadastro.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'App',
    data(){
      return {
              nomeField: "",
              emailField: "",
              cpfField: "",
              endereçoField: "",
              cepField: "",
              estadoField:"",
              cidadeField:"" ,
              nomeCField:"",
              numeroCField:"",
              dataEField: "",
              passwordField:"",
            
        clientes: [{
              id: 1,
              nomeField: "Geice Gomes",
              emailField: "sogmesmo@gmail.com",
              cpfField: "4654654",
              endereçoField: "",
              cepField: "",
              estadoField:"",
              cidadeField: "bhuasfuihai" ,
              nomeCField:"",
              numeroCField:"",
              dataEField: "",
              passwordField:""
        },
           
         ] 
       }
    },

   methods:{
        salvar: function(){
          if(this.nomeField == "" || this.nomeField ){
              console.log("erro");
          }else{
            this.clientes.push({  
              nome: this.nomeField,
              email: this.emailField,
              cpf: this.cpfField,
              endereço: this.endereçoField,
              cep: this.cepField,
              estado: this.estadoField,
              cidade: this.cidadeField,
              nomeC: this.nomeCField,
              numeroC: this.numeroCField,
              dataE: this.dataEField,
              password: this.passwordField,
              id: Date.now(),
            })
             this.nomeField = "";
             this.emailField = "";
             this.cpfField = "";
             this.endereçoField = "";
             this.estadoField = "";
             this.cepField = "";
             this.cidadeField = "";
             this.numeroCField = "";
             this.nomeCField = "";
             this.dataEField = "";
             this.passwordField = "";
        }
        }
    },

    components: {
           Menu,
           Cadastro,
           Footer 
  }
}
     

</script>

<style>
 h1 { 
     padding: 20px;
     display: flex;
     justify-content: center;
     color: #445566;
     font-family: Georgia, 'Times New Roman', Times, serif;
     background-color: #EFF4F9;
     margin: 0;
 }

 #form {   
        display: grid;
        justify-content: center;
        margin: 50px;
        padding: 0px 0px 0px 20%
            
 }
 
 .input{
     margin: 20px;
     height: 30px;
     width: 40vw;

     display: flex;
     align-items: center;
     justify-content: center;

     border-radius: 10px 20px;
     background-color: #EFF4F9;
 }
/* css dos inputs de endereço*/
 .inputend {
     margin: 10px 5px 10px 5px;
     height: 30px;
     width: 20vw;
     border-radius: 10px 20px;
     background-color: #EFF4F9;

 }
 #end { 
     display: flex;
     flex-flow: row wrap;
     
 }
 .colun1 {
     width: 20%;
 }
 .colun2 {
     margin-left: 10%;
     width: 20%;
 }

 /* css Forma de pagamento*/
 #pagamento {
     margin: 10px 25px 15px 25% ;
     display: flow-root;
     align-items: center;
     justify-content: center;
     
 }

 #end {
     margin-top: 30px;
 }
 .inputC {
     margin: 10px 5px 10px 5px;
     height: 30px;
     width: 20vw;
     border-radius: 10px 20px;
     background-color: #EFF4F9;
 }
 h4 { display: flex;
    justify-content: center;
    

 }
 button { 
     margin-left:  40%;
     height: 30px;
     width: 20vw;  
     background: #1188EE;
     color: white;
     box-shadow: 0px 2px 2px;
     border-radius:20px 20px ;
     text-align: center;
     font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
    

 }
  #listaT {
      width: 50% ;
      margin-left: 25%;
  
 }
 th{
    border-bottom: 1px solid #ddd;
}
</style>

