<template>
    <section id="album-container">
        <div class="col" v-for="(album, index) in albums" :key="index">
            <Card :album="album"/>
        </div>
    </section>
</template>

<script>
import axios from "axios";
import Card from "./Card.vue";
export default {
    name: "AlbumContainer",
    components: {
        Card
    },
    data(){
        return {
            albums: [] 
        }
    },
    created(){
        axios.get("https://flynn.boolean.careers/exercises/api/array/music").then((res) => {
            this.albums = res.data.response;
        })
}
}
</script>

<style scoped lang="scss">
#album-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
   .col {
       width: 20%;
   }
}
</style>