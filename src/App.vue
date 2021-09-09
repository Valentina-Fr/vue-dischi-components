<template>
  <div id="app">
    <Header />
    <main class="container">
      <AlbumContainer>
        <Card />
      </AlbumContainer>
    </main>
  </div>
</template>

<script>
import Header from "@/components/Header.vue";
import AlbumContainer from "@/components/AlbumContainer.vue";
import Card from "@/components/Card.vue";
export default {
  name: 'App',
  components: {
    Header,
    AlbumContainer,
    Card,
  }
}
</script>

<style lang="scss">
@import "/scss/style.scss";
</style>
