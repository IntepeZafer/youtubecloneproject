<template>
  <ul class="video-list-container">
    <li class="video-list-item" @click="onVideoSelect">
      <img :src="imageUrl">
      <p>{{videos.snippet.title}}</p>
    </li>
  </ul>
</template>

<script>
export default {
    name : 'VideoListItemCompenent',
    data(){
        return {}
    },
    props:["videos"],
    emits : ['videoSelect'],
    computed : {
        imageUrl(){
            return this.videos.snippet.thumbnails.medium.url
        },
    },
    methods : {
        onVideoSelect(){
            this.$emit('videoSelect', this.videos)
            console.log(this.videos)
        }
    }
}
</script>

<style>
  .video-list-container{
    display: flex;
    border: 1px solid black;
    margin-top: 1rem;
    padding: 1rem;
    border-radius: 0.3rem;
  }
  .video-list-item{
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 1rem;
  }
  .video-list-item img{
    object-fit: cover;
    border-radius: 0.3rem;
  }
</style>