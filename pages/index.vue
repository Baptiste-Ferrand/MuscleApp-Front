<template>
  <div>
    <div class="card">
      <weight-card
        title="Poids Initial"
        subtitle="60 KG"
      />
      <weight-card
        title="Poids Actuel"
        subtitle="80 KG"
      />
      <weight-card
        title="Poids Final"
        subtitle="90 KG"
      />
      <weight-card
        title="Objectif"
        subtitle="PDM"
      />
    </div>
    <graph-stats-weight/>
  </div>
</template>

<script>
import GraphStatsWeight from "~/components/GraphStatsWeight.vue";
import WeightCard from "~/components/WeightCard.vue";

export default {
  name: 'IndexPage',
  components: { WeightCard, GraphStatsWeight},
}
</script>

<style scoped>
.card{
  display: flex;
  margin-left: 25px;
  align-items: center;
  justify-content: center;
  margin-bottom: 30px;
  margin-top: 20px;
}
</style>
