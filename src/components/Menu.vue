<template>
    <header>
        <img src="@/assets/tsa-logo.png" alt="Logo">
        <Navbar/>
        
    </header>
</template>
 
 
<script>


import Navbar from './Navbar.vue';

export default {
    name: 'menu',
    components: {
        Navbar      
    }   
}
</script>

<style scoped>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
header {
    display: flex;
    align-items: flex-start;
    justify-content: space-between;
    width: 100vw;
    background-color:#17222D ;
    padding: 15px;
}
 header img {
     max-width: 200px;
     
 }


</style>