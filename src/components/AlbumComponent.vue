32 lines (26 sloc)  532 Bytes
   
<template>
 <div class="ms_album text-center">
  <img class="img-fluid pt-2 pb-2" :src="album.poster" :alt="album.title" />
  <h5 class="fw-bold p-1">{{ album.title.toUpperCase() }}</h5>
  <div class="p-1">
   <p>{{ album.author }}</p>
   <p>{{ album.year }}</p>
  </div>
 </div>
</template>

<script>
export default {
 name: "AlbumComponent",
 props: ["album"],
};
</script>

<style lang="scss" scoped>
@import "@/assets/scss/variables.scss";
.ms_album {
 h5 {
  color: $albumTitleColor;
 }
 p {
  margin: 0;
  color: $subtitleColor;
 }
}
</style>