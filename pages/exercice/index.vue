<template>
  <div>
    <div>
      <span>Exercice Name</span>
      <span>Description de l'exercice, quelque conseil etc</span>
    </div>
    <div>
      <video-player src="https://www.youtube.com/watch?v=XMycI9c3amg" />
    </div>
  </div>
</template>

<script>
import VideoPlayer from 'nuxt-video-player'

require('nuxt-video-player/src/assets/css/main.css')
export default {
  components: { VideoPlayer },
}
</script>
