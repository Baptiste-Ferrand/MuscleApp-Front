<template>
  <div>
    <div class="card">
      <weight-card
        :subtitle="user.first_weight.toFixed(1)"
        title="Poids Initial"
      />
      <weight-card subtitle="80 KG" title="Poids Actuel" />
      <weight-card subtitle="90 KG" title="Poids Final" />
      <weight-card subtitle="PDM" title="Objectif" />
    </div>
    <graph-stats-weight />
    <video-player src="https://www.youtube.com/watch?v=IzDbhbwrd_0" />
  </div>
</template>

<script>
import VideoPlayer from 'nuxt-video-player'
import GraphStatsWeight from '~/components/GraphStatsWeight.vue'
import WeightCard from '~/components/WeightCard.vue'

require('nuxt-video-player/src/assets/css/main.css')
export default {
  name: 'IndexPage',
  components: { WeightCard, GraphStatsWeight, VideoPlayer },
  data() {
    return {
      user: {
        first_weight: 0,
      },
    }
  },
  async fetch() {
    await this.$axios.get('weight/initial').then((response) => {
      this.user.first_weight = response.data.value
    })
  },
}
</script>

<style scoped>
.card {
  display: flex;
  margin-left: 25px;
  align-items: center;
  justify-content: center;
  margin-bottom: 30px;
  margin-top: 20px;
}
</style>
