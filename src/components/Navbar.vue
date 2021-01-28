<template>
    <nav>
      <div class="menu-item"><a href="#">Lista</a></div>
      <div class="menu-item"><a href="#">Cadastro</a></div> 
    </nav>
</template>

<script>


export default {
    name: 'navbar',
    data () {
        return
    }
}
</script>

<style scoped>
 nav {
     display: flex;
     align-items: center;
     justify-content:flex-end;
 }
 nav .menu-item {
     color: #fff;
     padding: 10px 20px;
     position: relative;
     text-align: center;
     border-bottom: 3px solid transparent;
     display: flex;
     transition: 0.4s;

 }
 nav .menu-item.active,
 nav .menu-item:hover{
     background-color:#445566 ;
     border-bottom-color: #EFF4F9;
 }

 nav .menu-item a {
    
     color : inherit;
     text-decoration: none;
     font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
 }
</style>

