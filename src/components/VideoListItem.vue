<template>
  <li class="list-group-item media" @click="onVideoSelect">
    <img class="mr-3" :src="thumbnailUrl" />
    <div class="media-body">{{video.snippet.title}}</div>
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
  },
  methods: {
    onVideoSelect: function() {
      this.$emit("videoSelect", this.video); //video is the prop by parent
    }
  }
};
</script>


<style scoped>
li {
  display: flex; /*to get image and heading in same line */
  cursor: pointer;
}
li:hover {
  background-color: #eee;
}
</style>