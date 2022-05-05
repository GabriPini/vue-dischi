<template>
 <main class="ps-5 pe-5">
  <section class="container p-5">
   <div v-if="visualize" class="row p-5">
    <div
     v-for="(element, index) in albumList"
     :key="index"
     class="col-2 m-3 my_album-box"
    >
     <AlbumBox :album="element" />
    </div>

    <div></div>
   </div>

   <div v-else class="row my_loader">
    <div class="col-12 text-center">
     <h1 class="text-white">LOADING</h1>
     <img 
      src="https://uxwing.com/wp-content/themes/uxwing/download/07-web-app-development/loader.png"
      alt=""
     />
    </div>
   </div>
  </section>
 </main>
</template>
<script>
import axios from "axios";
import AlbumBox from "@/components/AlbumComponent.vue";
export default {
 name: "MainComponent",

 components: {
  AlbumBox,
 },

 data: function () {
  return {
   albumList: [],
   visualize: false,
  };
 },
 created: function () {
  axios
   .get("https://flynn.boolean.careers/exercises/api/array/music")
   .then((answer) => {
    this.albumList = [...answer.data.response];
   });
  setTimeout(() => {
   this.visualize = true;
  }, 2500);
 },
};
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "@/assets/scss/variables.scss";
@keyframes rotation {
 0% {
  transform: rotate(0deg);
 }
 100% {
  transform: rotate(360deg);
 }
}
main {
 min-height: calc(100vh - 75px);
 background-color: $mainBgColor;
 .my_album-box {
  background-color: $albumBgColor;

  p {
   color: $subtitleColor;
  }
 }
 .my_loader {
  img {
   height: 150px;
   width: 150px;
   animation-name: rotation;
   animation-duration: 1.25s;
   animation-iteration-count: infinite;
   animation-timing-function: linear;
   filter: invert(1);
  }
 }
}
</style>