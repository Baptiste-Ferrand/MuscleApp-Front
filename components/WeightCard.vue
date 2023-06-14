<template>
  <v-card class="card">
    <v-card-title>{{title}}</v-card-title>
    <v-card-subtitle>{{subtitle}}</v-card-subtitle>
  </v-card>
</template>

<script>
export default {
  name: "WeightCard",
  props:{
    title:{
      type: String,
      default: ''
    },
    subtitle:{
      type: String,
      default: ''
    }
  }
};
</script>

<style scoped>
v-card-subtitle{
  align-content: center;
}
.card{
  align-content: center;
  height: 10%;
  width: 15%;
  border-radius: 25px;
  background: radial-gradient(#000000,  #2c5a57);

}

</style>
