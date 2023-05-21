<template>
  <v-card
    max-width="1200"
    class="mx-auto"
  >
    <v-container>
      <v-item-group
        multiple
      >
        <v-row>
          <v-col
            v-for="(item, i) in items"
            :key="i"
            cols="9"
            md="3"
            @click="test(item)"
          >
            <v-item>
              <v-img
                :src="item.src"
                cover
                height="150"
                class="text-right pa-2"
              />
            </v-item>
          </v-col>
        </v-row>
      </v-item-group>
    </v-container>
  </v-card>
</template>
<script>
export default {
  name: 'Infomachine',
  data () {
    return {
      items: [
        {
          name: 'Biceps',
          src: require('~/assets/img/corps_humain/biceps/Biceps.png'),
          to: '/corps-humains/biceps'
        },
        {
          name: 'Triceps',
          src: require('~/assets/img/corps_humain/triceps/260px-Triceps_brachii.png'),
          to: '/corps-humains/triceps'
        },
        {
          name: 'Ishio',
          src: 'backgrounds/bg-2.jpg',
          to: '/corps-humains/ishio'
        },
        {
          name: 'Quadriceps',
          src: require('~/assets/img/corps_humain/pec.jpg'),
          to: '/corps-humains/quadriceps'
        },
        {
          name: 'Molet',
          src: require('~/assets/img/corps_humain/pec.jpg'),
          to: '/corps-humains/mollet'
        },
        {
          name: 'Epaule',
          src: require('~/assets/img/corps_humain/pec.jpg'),
          to: '/corps-humains/epaule'
        },
        {
          name: 'Dos',
          src: require('~/assets/img/corps_humain/pec.jpg'),
          to: '/corps-humains/dos'
        },
        {
          name: 'Pec',
          src: require('~/assets/img/corps_humain/pec.jpg'),
          to: '/corps-humains/pec'
        },
        {
          name: 'Abdos',
          src: require('~/assets/img/corps_humain/pec.jpg'),
          to: '/corps-humains/abdos'
        },
        {
          name: 'Tandon',
          src: require('~/assets/img/corps_humain/pec.jpg'),
          to: '/corps-humains/tandon'
        }, {
          name: 'Artiulation',
          src: require('~/assets/img/corps_humain/pec.jpg'),
          to: '/corps-humains/articulation'
        }
      ]
    }
  },
  methods: {

    test (item) {
      switch (item.name) {
        case 'Biceps':
          this.$router.push(this.localePath(item.to))
          break
        case 'Triceps':
          this.$router.push(this.localePath(item.to))
          break
        case 'Ishio':
          this.$router.push(this.localePath(item.to))
          break
        case 'Quadriceps':
          this.$router.push(this.localePath(item.to))
          break
        case 'Molet':
          this.$router.push(this.localePath(item.to))
          break
        case 'Epaule':
          this.$router.push(this.localePath(item.to))
          break
        case 'Dos':
          this.$router.push(this.localePath(item.to))
          break
        case 'Pec':
          this.$router.push(this.localePath(item.to))
          break
        case 'Abdos':
          this.$router.push(this.localePath(item.to))
          break
        case 'Tandon':
          this.$router.push(this.localePath(item.to))
          break
        case 'Artiulation':
          this.$router.push(this.localePath(item.to))
          break
        default:
          break
      }
    }
  }

}
</script>

<style scoped>

</style>
