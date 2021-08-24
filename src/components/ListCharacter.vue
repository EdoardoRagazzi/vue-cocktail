<template>
  <div class="listCharacter"></div>
</template>

<script>
// IMPORT AXIOS FOR USE API
import axios from "axios";

export default {
  name: "ListCharacter",
},
data(){
    return{
        apiURL:'https://flynn.boolean.careers/exercises/api/array/music',
        listCocktails: [],
    }
}
</script>

<style lang='scss' scoped>
@import "@/style/common.scss";
</style>