<template>
  <div class="main">
    <div class="split left">
      <video autoplay muted loop id="myVideo">
        <h3>Cocktails</h3>
        <source src="../assets/smokey_glass.mp4" type="video/mp4" />
      </video>
    </div>
    <div class="split right">
      <video autoplay muted loop id="myVideo">
        <h3>Ingredients</h3>
        <source src="../assets/drink_spruzz.mp4" type="video/mp4" />
      </video>
    </div>

    <ListCocktail />
  </div>
</template>

<script>
import ListCocktail from "@/components/ListCocktail.vue";

export default {
  name: "Main",
  components: {
    ListCocktail,
  },
};
</script>


<style scoped lang="scss">
@import "@/style/common.scss";

.main {
  position: relative;
  width: 100%;
  height: 100vh;
  background: #333;
}
.split {
  position: absolute;
  width: 50%;
  height: 100%;
  overflow: hidden;
}
.split.left {
  left: 0;
}
#myVideo {
  width: 100%;
  height: 100vh;
  object-fit: cover;
  z-index: -100;
}
h3 {
  z-index: 99;
}
.split.left::before {
  content: "";
  position: absolute;
  width: 100%;
  height: 100%;
  background-color: rgba(87, 84, 236, 0.7);
}
.split.right {
  right: 0;
  background-repeat: no-repeat;
  background-size: cover;
}
.split.right::before {
  content: "";
  position: absolute;
  width: 100%;
  height: 100%;
  background-color: rgba(43, 43, 43, 0.8);
}
</style>
