<template>
    <div>
       <h1>Cadastro</h1>
        <div id="form">
         <div id="info">
             <label for="Nome">Nome</label>
             <input type="text" id="nome" class="input">

             <label for="email">Email</label>
             <input type="text" id="email" class="input">

             <label for="cpf">CPF</label>
             <input type="text" id="cpf" class="input">
         </div> 
         <div id="end">
         <div class="colun1">
             <label for="endereço">Endereço</label>
             <input type="text" id="endereço" class="inputend"> 

             <label for="estado">Estado</label>
             <input type="text" id="endereço" class="inputend"> 
         </div>
         <div class="colun2">
             <label for="cep">CEP</label>
             <input type="text" id="cep" class="inputend"> 

             <label for="cidade">Cidade</label>
             <input type="text" id="cidade" class="inputend"> 
         </div> 
           </div>
        </div>
        <h1>  Forma de Pagamento </h1>  
         <div id="pagamento">  
            <label for="male">
                <input type="radio" id="male" value="Male" v-model="radioBoxOption"> Cartao de Credito
           </label>
           <label for="female"> <input type="radio"  id="female" value="Female" v-model="radioBoxOption"> Boleto Bancario
           </label>
           <div id="end">
         <div class="colun1">
             <label for="nomeC">Nome no Cartão</label>
             <input type="text" id="nomeC" class="inputC"> 

             <label for="numeroC">Número da Cartão</label>
             <input type="number" id="endereço" class="inputC"> 
         </div>
         <div class="colun2">
             <label for="dataE">Data de Expiração</label>
             <input type="number" id="DataE" class="inputC"> 

             <label for="password">Código de Segurança</label>
             <input type="password" id="password" class="inputC"> 
             
         </div> 
           
           </div>
           
            </div> 
          <h4>Seu cartão será debitado em R$ 49,00</h4>
            <input id="button" type="buttom" value="REALIZAR MATRÍCULA" />
    </div>
</template>

<script>
export default {
    data(){
        return {
        useData:{
            nome:''
    
        }      
      }
    }
}
</script>

<style scoped>
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
 #button { 
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
</style>