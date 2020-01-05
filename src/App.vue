<template>
  <div>
    <SearchBar @termChange="onTermChange"></SearchBar>
    <VideoList :videos="videos"></VideoList>
    <!--similar to @ but for data from parent to child-->
    <!-- v-bind can have any name and the second videos is what we specify in the data property-->
  </div>
</template>

<script>
import VideoList from "./components/VideoList";
import axios from "axios";
import SearchBar from "./components/SearchBar";
const API_KEY = "AIzaSyBv7FWfP6FovESylWSvZiPCrYc45EobAyE";
export default {
  name: "App", //no need for el it will automatically understand
  components: {
    SearchBar: SearchBar, //you can only write searchBar instead of SearchBar:SearchBar coz key and value are same
    VideoList: VideoList
  },
  data: function() {
    return { videos: [] }; //should know what the data must contain
  },
  methods: {
    onTermChange: function(searchTerm) {
      axios
        .get("https://www.googleapis.com/youtube/v3/search", {
          params: {
            key: API_KEY,
            type: "video",
            part: "snippet",
            q: searchTerm
          }
        })
        .then(response => {
          this.videos = response.data.items; // data is not related to our instance, its from Youtube API response (check out in ctrl+SHIFT+I)
        });
    }
  }
};
</script>