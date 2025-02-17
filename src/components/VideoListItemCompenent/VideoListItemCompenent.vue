<template>
  <ul>
    <li><img :src="imageUrl"></li>
  </ul>
</template>

<script>
export default {
    name : 'VideoListItemCompenent',
    data(){
        return {}
    },
    props:["videos"],
    computed : {
        imageUrl(){
            return this.videos.snippet.thumbnails.medium.url
        }
    }
}
</script>

<style>

</style>