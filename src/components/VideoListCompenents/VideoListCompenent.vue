<template>
  <ul>
    <VideoListItemCompenent @videoSelect="onVideoSelect" v-for="videos in videos" :key="videos.etag" :videos="videos"/>
  </ul>
</template>

<script>
import VideoListItemCompenent from '../VideoListItemCompenent/VideoListItemCompenent.vue'
export default {
    name : 'VideoListCompenent',
    data(){
        return{}
    },
    emits : ['videoSelect'],
    props : ['videos'],
    methods : {
        onVideoSelect(videos){
            this.$emit('videoSelect', videos)
        }
    },
    components : {
        VideoListItemCompenent
    },
}
</script>

<style scoped>

</style>