<template>
 <header class="d-flex align-items-center">
  <img
   class="ms-3"
   src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/19/Spotify_logo_without_text.svg/768px-Spotify_logo_without_text.svg.png"
   alt="spotify logo"
  />
 </header>
</template>

<script>
export default {
 name: "HeaderComponent",
};
</script>

<style lang="scss" scoped>
@import "@/assets/scss/variables.scss";
header {
 height: 75px;
 background-color: $headerBgColor;

 img {
  height: 60px;
 }
}
</style>