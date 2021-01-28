<template>
  <footer>
    <img src="@/assets/meu-logo.png" alt="meu-Logo">
    <h1> 2021 </h1>
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
footer h1 {
    margin-top: 60px;
    padding: 20px;
    color: #fff;
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Roboto', Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
    font-size: 100%;
}
</style>