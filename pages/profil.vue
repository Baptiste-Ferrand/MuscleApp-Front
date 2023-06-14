<template>
<div>
  <v-card class="background">
    <v-card-title>
      <span class="text-h5">User Profile</span>
    </v-card-title>
    <v-card-text>
      <v-container>
        <v-row>
          <v-col
            cols="12"
            sm="6"
            md="4"
          >
            <v-text-field
              label="Prénom"
              required
              outlined
            ></v-text-field>
          </v-col>
          <v-col
            cols="12"
            sm="6"
            md="4"
          >
            <v-text-field
              label="Nom"
              outlined
            ></v-text-field>
          </v-col>
          <v-col
            cols="12"
            sm="6"
            md="4"
          >
            <v-select
              :items="items"
              label="Objectif"
              density="comfortable"
              outlined
            ></v-select>
          </v-col>
          <v-col cols="12">
            <v-text-field
              label="Email*"
              required
              outlined
            ></v-text-field>
          </v-col>
          <v-col cols="12">
            <v-text-field
              label="Password*"
              type="password"
              required
              outlined
            ></v-text-field>
          </v-col>
          <v-col
            cols="12"
            sm="4"
          >
            <v-text-field
              label="Poids initial"
              hint="Poids en KG"
              outlined
            ></v-text-field>
          </v-col>
          <v-col
            cols="12"
            sm="4"
          >
            <div>
            <v-text-field
              label="Poids actuel"
              hint="Poids en KG"
              outlined
            ></v-text-field>
            <v-btn>Ajouter</v-btn>
            </div>
          </v-col>
          <v-col
            cols="12"
            sm="4"
          >
            <v-text-field
              label="Poids final"
              hint="Poids en KG"
              outlined
            ></v-text-field>
          </v-col>
        </v-row>
      </v-container>
      <small>*indicates required field</small>
    </v-card-text>
    <v-card-actions>
      <v-btn>
        Sauvegarder
      </v-btn>
      <v-btn
        color="error"
        @click="gotoLogin">
        deconexion
      </v-btn>
    </v-card-actions>
  </v-card>
</div>

</template>

<script>
export default {
  name: "Profil",
  data(){
    return {
      items: ['Prise de masse', 'sèche', 'perte de poids', 'renforcement', 'maintient']
    }
  },
  methods:{
    gotoLogin(){
      this.$router.push('/login')
    }
  }
}
</script>

<style scoped>
.background{
  background: #0a0a14;
}
</style>
