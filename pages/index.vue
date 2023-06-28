<template>
  <div>
    <div class="card">
      <weight-card
        :subtitle="parseInt(user.first_weight.toFixed(1))"
        title="Poids Initial"
      />
      <weight-card
        :subtitle="parseInt(user.actual_weight)"
        title="Poids Actuel"
      />
      <weight-card :subtitle="parseInt(user.last_weight)" title="Poids Final" />
      <weight-card :subtitle="user.objectif" title="Objectif" />
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
        actual_weight: 0,
        last_weight: 0,
        objectif: '',
      },
    }
  },
  async fetch() {
    await this.$axios.get('weight/initial').then((response) => {
      this.user.first_weight = response.data.value
    })
    await this.$axios.get('weight/latest').then((response) => {
      this.user.actual_weight = response.data.value
    })
    await this.$axios.get('objective').then((response) => {
      this.user.objectif = response.data[0].title
      this.user.last_weight = response.data[0].weight
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
