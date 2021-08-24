<template>
  <div class="listCharacter">
    <div v-for="(item, index) in listCocktails" :key="index"></div>
  </div>
</template>

<script>
// IMPORT AXIOS FOR USE API
import axios from "axios";

export default {
  name: "ListCharacter",

  data() {
    return {
      apiKey: "1",
      apiURL:
        "https://www.thecocktaildb.com/api/json/v1/1/search.php?s=martini",
      listCocktails: [],
      searchCocktail: "martini",
    };
  },
  created() {
    this.getCocktails();
  },
  methods: {
    getCocktails() {
      const request = {
        params: {
          api_key: this.apiKey,
          query: this.searchCocktail,
        },
      };

      axios.get(this.apiURL, request).then((res) => {
        console.log(res);
        this.listCocktails = res.data;
        console.log(this.listCocktails);
      });
    },
  },
};
</script>

<style lang='scss' scoped>
@import "@/style/common.scss";
</style>