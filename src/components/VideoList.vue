<template>
  <ul>
    <VideoListItem v-for="video in videos" :video="video"></VideoListItem>
  </ul>
</template>


<script>
import VideoListItem from "./VideoListItem";
export default {
  name: "VideoList",
  components: {
    VideoListItem: VideoListItem
  },
  props: ["videos"] //array of strings which are exact property names of data which they should expect
  //same as what we gave in app.vue with :
};
</script>


<style>
</style>