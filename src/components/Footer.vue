<template>
  <footer>
    <img src="@/assets/meu-logo.png" alt="meu-Logo">
    
  </footer>
</template>

<script>


export default {
    name: 'footer',
    data () {
        return
    }
}
</script>

<style scoped>
footer {
    display: flex;
    align-items: flex-start;
    justify-content: space-between;
    margin: 10px;
    padding: 0;
    box-sizing: border-box;
    width: 100vw;
    background-color:#17222D ;
}
footer img {
    margin: 20px;
     max-width: 300px;
}
</style>