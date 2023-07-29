<template>
  <iframe
    width="450"
    height="315"
    :src="`https://player.vimeo.com/video/${props.videoId}`"
    title="video player"
    frameborder="0"
    allow="accelerometer; autoplay; clipboard-write; ecncrypted-media"
    allowfullscreen 
  ></iframe>
</template>
<script setup>
const props = defineProps({
    videoId : {
        type : Number,
        required : true
    }
})
</script>