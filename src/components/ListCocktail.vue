<template>
  <div class="lista">
    <div v-for="(item, index) in listCocktails" :key="index"></div>
  </div>
</template>

<script>
// IMPORT AXIOS FOR USE API
import axios from "axios";

export default {
  name: "ListCocktail",

  data() {
    return {
      apiKey: "1",
      apiURL: "https://www.thecocktaildb.com/api/json/v1/1/search.php?",
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
          s: this.searchCocktail,
        },
      };

      axios.get(this.apiURL, request).then((res) => {
        /* this.listCocktails = res.data.drinks; */

        // CON UN CICLO FOR CICLIAMO L'ARRAY E PUSHAMO OGNI ELEMENTO
        // for (var i = 0; i < res.data.drinks.length; i++) {
        //   this.listCocktails.push(res.data.drinks[i].strDrink);
        // }
        // console.log(this.listCocktails);

        // FUNZIONAAAAA  For each element push
        res.data.drinks.forEach((elem) =>
          this.listCocktails.push(elem.strDrink)
        );
      });
    },
  },
};
</script>

<style lang='scss' scoped>
@import "@/style/common.scss";
</style>