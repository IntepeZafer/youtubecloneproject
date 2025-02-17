<template>
  <div v-if="video">
    <div>
        <iframe :src="videoUrl"></iframe>
    </div>
    <div>
        <h4>{{video.snippet.title}}</h4>
        <p>{{video.snippet.description}}</p>
    </div>
  </div>
</template>

<script>
export default {
    name : 'VideoDetailsCompenent',
    data() {
        return {}
    },
    props : ['video'],
    methods : {
        onVideoSelect(){
            this.$emit('videoSelect')
            console.log(this.video.snippet.title)
        }
    },
    computed : {
        videoUrl(){
            return 'https://www.youtube.com/embed/' + this.video.id.videoId
        }
    }
}
</script>

<style>

</style>