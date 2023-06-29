<template>
  <div>
    <div align="center">
      <span class="text-h2">{{ exercice.name }}</span> <br />
      <span>{{ exercice.description }}</span>
    </div>
    <div>
      <video-player :src="exercice.video" />
    </div>
  </div>
</template>

<script>
import VideoPlayer from 'nuxt-video-player'

require('nuxt-video-player/src/assets/css/main.css')
export default {
  components: { VideoPlayer },
  data() {
    return {
      exercice: {
        name: '',
        description: '',
        video: '',
      },
    }
  },
  async fetch() {
    await this.$axios
      .get('exercise/' + this.$route.query.id)
      .then((response) => {
        this.exercice.name = response.data.title
        this.exercice.description = response.data.description
        this.exercice.video = response.data.video
      })
  },
}
</script>
