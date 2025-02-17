<template>
  <div class="container">
    <h1 class="title">Youtube Clone Project</h1>
    <SearchBarCompenent VideoListCompenent = "VideoListCompenent" @search="searchTerm"/>
    <VideoListCompenent :videos="videos"/>
  </div>
</template>

<script>
import SearchBarCompenent from './components/SearchBarCompenent/SearchBarCompenent.vue';  
import VideoListCompenent from './components/VideoListCompenents/VideoListCompenent.vue';
import axios from 'axios';
export default {
  name: 'App',
  components: {
    SearchBarCompenent,
    VideoListCompenent
  },
  data(){
    return{
      videos : []
    }
  },
  methods: {
    searchTerm(searchTerm) {
      axios.get('https://www.googleapis.com/youtube/v3/search' , {
        params : {
          part : 'snippet',
          type : 'video',
          key : 'AIzaSyBpm-udD3Brq-ajji77qv5PRG8XIQCUMOo',
          query : searchTerm
        }
      })
      .then(response => {
        this.videos = response.data.items
        console.log(this.videos)
      })
      .catch(error => {
        console.log(error);
      })
    }  
  }
}
</script>

<style>
  *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    text-decoration: none;
    list-style: none;
    font-family: Arial, Helvetica, sans-serif;
    scroll-behavior: smooth;
  }
  .container {
    max-width: 75rem;
    width: 100%;
    background-color: rgb(255, 255, 255);
    margin: 3.125rem auto;
    font-size: 24px;
    padding: 1rem;
    box-shadow: 0 0 20px 0 rgba(0, 0, 0, 0.2), 0 5px 5px 0 rgba(0, 0, 0, 0.24);
  }
  .container h1{
    text-align: center;  
    font-weight: 100;
    font-size: 1em;
    letter-spacing: .125rem;
    text-transform: capitalize;
  }
</style>
