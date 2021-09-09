<template>
    <div id="genre-select">
        <select name="genres" id="genres" v-model="musicGenre" @change="$emit('lookUp', musicGenre)">
            <option>All</option>
            <option>Rock</option>
            <option>Pop</option>
            <option>Metal</option>
            <option>Jazz</option>
        </select>
    </div>
</template>

<script>
export default {
    name: "Search",
    data(){
      return {
        musicGenre:"All",
      }
    }
}
</script>

<style scoped lang="scss">
#genre-select {
  text-align: right;
  margin: 20px;
}

#genres {
  background-color: #2e3a46;
  color: white;
  border-radius: 3px;
  width: 100px;
  height: 30px;
}
</style>