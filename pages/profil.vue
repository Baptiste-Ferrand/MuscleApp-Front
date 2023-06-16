<template>
  <div>
    <v-card class="background">
      <v-card-title>
        <span class="text-h5">User Profile</span>
      </v-card-title>
      <v-card-text>
        <v-container>
          <v-row>
            <v-col cols="12" md="4" sm="6">
              <v-text-field
                v-model="user.name"
                label="Prénom"
                outlined
                required
              ></v-text-field>
            </v-col>
            <v-col cols="12" md="4" sm="6">
              <v-text-field
                v-model="user.surname"
                label="Nom"
                outlined
              ></v-text-field>
            </v-col>
            <v-col cols="12" md="4" sm="6">
              <v-select
                v-model="user.objectif"
                :items="items"
                density="comfortable"
                label="Objectif"
                outlined
              ></v-select>
            </v-col>
            <v-col cols="12">
              <v-text-field
                v-model="user.email"
                label="Email"
                outlined
                required
              ></v-text-field>
            </v-col>
            <v-col cols="12">
              <v-text-field
                v-model="user.password"
                label="Password*"
                outlined
                required
                type="password"
              ></v-text-field>
            </v-col>
            <v-col cols="12" sm="4">
              <v-text-field
                v-model="user.first_weight"
                disabled
                hint="Poids en KG"
                label="Poids initial"
                outlined
              ></v-text-field>
            </v-col>
            <v-col cols="12" sm="4">
              <div>
                <v-text-field
                  v-model="user.actual_weight"
                  hint="Poids en KG"
                  label="Poids actuel"
                  outlined
                ></v-text-field>
                <v-btn @click="addWeight">Ajouter</v-btn>
              </div>
            </v-col>
            <v-col cols="12" sm="4">
              <v-text-field
                v-model="user.last_weight"
                hint="Poids en KG"
                label="Poids final"
                outlined
              ></v-text-field>
            </v-col>
          </v-row>
        </v-container>
        <small>*indicates required field</small>
      </v-card-text>
      <v-card-actions>
        <v-btn @click="updateProfil"> Sauvegarder</v-btn>
        <v-btn color="error" @click="gotoLogin"> deconexion</v-btn>
      </v-card-actions>
    </v-card>
  </div>
</template>

<script>
import moment from 'moment/moment'

export default {
  name: 'Profil',
  data() {
    return {
      user: {
        id: 0,
        name: '',
        surname: '',
        username: '',
        password: '',
        email: '',
        first_weight: 0,
        actual_weight: 0,
        last_weight: 0,
        objectif: '',
      },
      items: [
        'Prise de masse',
        'Sèche',
        'Perte de poids',
        'Renforcement',
        'Maintient',
      ],
    }
  },
  async fetch() {
    await this.$axios.get('user').then((response) => {
      this.user.id = response.data.id
      this.user.name = response.data.name
      this.user.surname = response.data.surname
      this.user.username = response.data.username
      this.user.email = response.data.email
    })
    await this.$axios.get('weight/initial').then((response) => {
      this.user.first_weight = response.data.value
    })
    await this.$axios.get('objective').then((response) => {
      this.user.objectif = response.data[0].title
      this.user.last_weight = response.data[0].weight
    })
  },
  methods: {
    async addWeight() {
      const data = {
        date: parseInt(moment(new Date()).format('X')),
        value: parseInt(this.user.actual_weight),
      }
      try {
        await this.$axios.post('weight', data).then((response) => {
          console.log(response)
        })
      } catch (e) {
        console.log(e)
      }
    },
    gotoLogin() {
      this.$router.push('/login')
    },
    async updateProfil() {
      try {
        const data = {
          name: this.user.name,
          surname: this.user.surname,
          username: this.user.username,
          password: this.user.password,
          email: this.user.email,
        }
        await this.$axios.put('user/' + this.user.id, data)
      } catch (e) {
        console.log(e)
      }
    },
  },
}
</script>

<style scoped>
.background {
  background: #0a0a14;
}
</style>
