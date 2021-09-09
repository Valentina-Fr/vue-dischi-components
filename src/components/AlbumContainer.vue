<template>
    <section>
        <Search @lookUp="search"/>
        <div id="album-container">
            <div class="col" v-for="(album, index) in filterGenre" :key="index">
                <Card :album="album"/>
            </div>
        </div>
    </section>
</template>

<script>
import axios from "axios";
import Card from "./Card.vue";
import Search from "./Search.vue";
export default {
    name: "AlbumContainer",
    components: {
        Card,
        Search
    },
    data(){
        return {
            albums: [],
            musicGenre: "All"
        }
    },
    methods: {
      search(genre){
        this.musicGenre = genre;
      }
    },
    computed: {
        filterGenre(){
            if(this.musicGenre == "All") return this.albums;
            return this.albums.filter ((album) => {
                return album.genre.includes(this.musicGenre);
            })
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