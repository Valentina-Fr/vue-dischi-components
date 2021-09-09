<template>
  <header>
      <div class="container">
        <img src="../assets/logo.png" />
      </div>
  </header>
</template>

<script>
export default {
    name: "Header",
}
</script>

<style scoped lang="scss">
header {
  background-color: #2e3a46;
  height: 70px;
  padding: 10px;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  
    img {
    height: 50px;
    }
}
</style>