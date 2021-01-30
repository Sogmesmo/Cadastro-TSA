<template>
<div>          
     <table id="listaT">
         <thead>
            <tr>
               <td>{{cliente.nome}}</td> 
               <td>{{cliente.email}}</td>  
               <td>{{cliente.cpf}}</td>  
               <td>{{cliente.cidade}}</td>  
            </tr>
            </thead>
     </table>
  </div> 
</template>

<script>
export default {
    data(){
        return {}
        },

        props: {
             cliente: Object
        },

}   

</script>

<style scoped>
 h1 { 
     margin-top: 50px;
     padding: 20px;
     display: flex;
     justify-content: center;
     color: #445566;
     font-family: Georgia, 'Times New Roman', Times, serif;
     background-color: #EFF4F9;
    
 }

 table {
      margin-left:  25%;
      width: 50%;      
 }
  tr,td {
      
      height: 50px;
      text-align: left; 
      
      padding: 15px;  
}
</style>