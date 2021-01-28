<template>
    <header>
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
    width: 100vw;
    background-color:#17222D ;
    padding: 15px;
}

</style>