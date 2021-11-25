<template>
  <header>
    <a href="">
        <img src="../assets/logo.png" alt=""> 
    </a>
  </header>
</template>

<script>
export default {
name: 'Header',

}
</script>

<style scoped lang="scss">
header {
    padding: 1rem 10px;
    display: flex;
    align-items: center;
    height: 65px;
    background-color: #2E3A46;
    img {
        max-width: 48px;
    }
}
</style>