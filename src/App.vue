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

             <label id="inputcpf" for="cpf">CPF   *</label>
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
            <label >
                <input type="radio" id="Credito" value="Cartao de Credito" v-model="picked"> Cartao de Credito
           </label>
           <label> <input type="radio"  id="Boleto" value="Boleto Bancario" v-model="picked"> Boleto Bancario
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
            <button @click="salvar"> REALIZAR MATRÍCULA</button><br><br>
            <small id="cpferro" v-show="erro"> PREENCHA CAMPOS OBRIGATORIOS *</small><br>
            <div>
                
            </div>
   
                <h1>Listas</h1><br><br>

                <input id="busca" type="text" placeholder="Buscar Nome" v-model="busca"><br><br><br>
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

         <div v-for="cliente in resultadoBusca" :key="cliente.id">
           
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

          busca: "",
          erro: false,
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
              nome: "Jane Castro",
              email: "janecastro@gmail.com",
              cpf: "222.333.666-48",
              endereço: "Rua Carmezia 89",
              cep: "",
              estado:"",
              cidade: "Betin" ,
              nomeC:"",
              numeroC:"",
              dataE: "",
              password:""
        },
        {
              id: 2,
              nome: "Geice Gomes",
              email: "sogmesmo@gmail.com",
              cpf: "111.888.856-18",
              endereço: "Rua Tamboril 692",
              cep: "",
              estado:"Minas Gerais ",
              cidade: "Belo Horizonte" ,
              nomeC:"----------",
              numeroC:"---------",
              dataE: "----------",
              password:"----------"
        },
        {
              id: 3,
              nome: "Debora Souto",
              email: "adebora@gmail.com",
              cpf: "181.878.656-19",
              endereço: "Rua campanha 55",
              cep: "",
              estado:" ",
              cidade: "Londrina" ,
              nomeC:"----------",
              numeroC:"---------",
              dataE: "----------",
              password:"----------"
        },
        {
              id: 4,
              nome: "Arthur Avelar",
              email: "avelar@gmail.com",
              cpf: "711.388.256-48",
              endereço: "Rua mococa 32",
              cep: "",
              estado:" ",
              cidade: "Rio de Janeiro" ,
              nomeC:"----------",
              numeroC:"---------",
              dataE: "----------",
              password:"----------"
        },
      {
              id: 5,
              nome: "Lucas Prates",
              email: "lucas@gmail.com",
              cpf: "111.222.856-18",
              endereço: "Rua lavanda 6",
              cep: "",
              estado:" Sao Paulo ",
              cidade: "Sao Paulo" ,
              nomeC:"----------",
              numeroC:"---------",
              dataE: "----------",
              password:"----------"
        },
           
         ] 
       }
    },

   methods:{
        salvar: function(){
            if( this.cpfField == "" ||  this.cpfField == " "){
            this.erro = true;
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
                this.erro = false;
        }
        }
    },

    computed: {
        resultadoBusca: function(){
            if(this.busca == '' || this.busca == ' '){
                return this.clientes;
            }else{
                return this.clientes.filter(cliente => cliente.nome == this.busca)
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
 #cpferro {
     margin-left: 40%;
     color: red;
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
    
 /* css lista/busca*/
 }
  #listaT {
      width: 50% ;
      margin-left: 25%;
  
 }
 th{
    border-bottom: 1px solid #ddd;
}
textarea:focus, input:focus, select:focus {
    outline: 0;
}

#busca {
     margin: 10px 5px 10px 5px;
     height: 30px;
     width: 40vw;
     border-radius: 10px 20px;
     background-color: #EFF4F9;
     margin-left: 28%;

}
</style>

