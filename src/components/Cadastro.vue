<template>
<div>          
     <table id="listaT">
            <tr>
               <td>{{cliente.nomeField}}</td>
               <td>{{cliente.emailField}}</td>
               <td>{{cliente.cpfField}}</td>
               <td>{{cliente.cidadeField}} - {{cliente.endereçoField}}</td>
            </tr>
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
            }
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

 #listaT {
      width: 50% ;
      margin-left: 25%;

     
    
 }
  td {
    border-bottom: 1px solid #ddd;
}
</style>