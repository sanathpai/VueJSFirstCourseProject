<template>
  <li class="list-group-item">
    <img :src="thumbnailUrl" />
    {{video.snippet.title}}
  </li>
</template>

<script>
export default {
  name: "VideoListItem",
  props: ["video"],
  computed: {
    thumbnailUrl: function() {
      return this.video.snippet.thumbnails.default.url;
      //we put this whenever we use prop
    }
  }
};
</script>


<style>
</style>