<template>
  <ul>
    <VideoListItemCompenent v-for="videos in videos" :key="videos.etag" :videos="videos"/>
  </ul>
</template>

<script>
import VideoListItemCompenent from '../VideoListItemCompenent/VideoListItemCompenent.vue'
export default {
    name : 'VideoListCompenent',
    data(){
        return{}
    },
    methods : {},
    components : {
        VideoListItemCompenent
    },
    props : ['videos']
}
</script>

<style scoped>

</style>