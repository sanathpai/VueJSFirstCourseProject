<template>
  <div v-if="video">
    <div>
      <iframe :src="videoUrl" />
    </div>
    <div class="details">
      <h4>{{video.snippet.title}}</h4>
      <p>{{video.snippet.description}}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "VideoDetail",
  props: ["video"],
  computed: {
    videoUrl: function() {
      const videoId = this.video.id.videoId;
    }
  }
};
</script>

<style scoped>
.deatils {
  margin-top: 10px;
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 4px;
}
</style>