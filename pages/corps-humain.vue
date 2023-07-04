<template>
  <div>
    <v-row class="d-flex justify-center ml-10">
      <v-col
        v-for="item of corps_humain"
        :key="item.id"
        class="d-flex justify-center ml-10"
        cols="9"
        md="3"
        @click="gotoMuscle(item)"
      >
        <v-card max-width="344">
          <v-img :src="item.img" height="200px"></v-img>
          <v-card-title>
            {{ item.name }}
          </v-card-title>
          <v-card-subtitle>
            {{ item.desc }}
          </v-card-subtitle>
        </v-card>
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  name: 'CorpsHumain',
  data() {
    return {
      corps_humain: [
        {
          name: 'Biceps',
          img: require('../assets/img/corp-humains/biceps.png'),
          desc: "petite description du muscle vite fait t'a vue pas plus hein",
          id: 1,
        },
        {
          name: 'Triceps',
          img: require('../assets/img/corp-humains/triceps.png'),
          desc: "petite description du muscle vite fait t'a vue pas plus hein",
          id: 2,
        },
        {
          name: 'Avant Bras',
          img: require('../assets/img/corp-humains/avbras.png'),
          desc: "petite description du muscle vite fait t'a vue pas plus hein",
          id: 3,
        },
        {
          name: 'Ischio',
          img: require('../assets/img/corp-humains/ishio.jpg'),
          desc: "petite description du muscle vite fait t'a vue pas plus hein",
          id: 4,
        },
        {
          name: 'Quadriceps',
          img: require('../assets/img/corp-humains/quadriceps.jpg'),
          desc: "petite description du muscle vite fait t'a vue pas plus hein",
          id: 5,
        },
        {
          name: 'Mollet',
          img: require('../assets/img/corp-humains/mollets.jpg'),
          desc: "petite description du muscle vite fait t'a vue pas plus hein",
          id: 6,
        },
        {
          name: 'Pectoraux',
          img: require('../assets/img/corp-humains/pec.png'),
          desc: "petite description du muscle vite fait t'a vue pas plus hein",
          id: 7,
        },
        {
          name: 'Epaule',
          img: require('../assets/img/corp-humains/epaule.png'),
          desc: "petite description du muscle vite fait t'a vue pas plus hein",
          id: 8,
        },
        {
          name: 'Dos',
          img: require('../assets/img/corp-humains/dos.png'),
          desc: "petite description du muscle vite fait t'a vue pas plus hein",
          id: 9,
        },
        {
          name: 'Abdos',
          img: require('../assets/img/corp-humains/abdos.jpg'),
          desc: "petite description du muscle vite fait t'a vue pas plus hein",
          id: 10,
        },
      ],
    }
  },
  methods: {
    gotoMuscle(item) {
      switch (item.name) {
        case 'Biceps':
          this.$router.push('/corps-humains/biceps')
          break
        case 'Triceps':
          this.$router.push('/corps-humains/triceps')
          break
        case 'Avant Bras':
          this.$router.push('/corps-humains/avant-bras')
          break
        case 'Ischio':
          this.$router.push('/corps-humains/ishio')
          break
        case 'Quadriceps':
          this.$router.push('/corps-humains/quadri')
          break
        case 'Mollet':
          this.$router.push('/corps-humains/mollet')
          break
        case 'Pectoraux':
          this.$router.push('/corps-humains/pec')
          break
        case 'Epaule':
          this.$router.push('/corps-humains/epaule')
          break
        case 'Dos':
          this.$router.push('/corps-humains/dos')
          break
        case 'Abdos':
          this.$router.push('/corps-humains/abdos')
          break
        default:
          console.log('default')
          break
      }
    },
  },
}
</script>
