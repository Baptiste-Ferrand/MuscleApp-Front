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
          src: 'backgrounds/bg-2.jpg',
          to: '/corps-humains/bras'
        },
        {
          name: 'Triceps',
          src: 'backgrounds/md.jpg',
          to: '/corps-humains/jambes'
        },
        {
          name: 'Ishio',
          src: 'backgrounds/bg-2.jpg',
          to: '/corps-humains/epaule'
        },
        {
          name: 'Quadriceps',
          src: require('~/assets/img/corps_humain/pec.jpg'),
          to: '/corps-humains/pec'
        },
        {
          name: 'Molet',
          src: require('~/assets/img/corps_humain/pec.jpg'),
          to: '/corps-humains/pec'
        },
        {
          name: 'Epaule',
          src: require('~/assets/img/corps_humain/pec.jpg'),
          to: '/corps-humains/pec'
        },
        {
          name: 'Dos',
          src: require('~/assets/img/corps_humain/pec.jpg'),
          to: '/corps-humains/pec'
        },
        {
          name: 'Abdos',
          src: require('~/assets/img/corps_humain/pec.jpg'),
          to: '/corps-humains/pec'
        }, {
          name: 'Tandon',
          src: require('~/assets/img/corps_humain/pec.jpg'),
          to: '/corps-humains/pec'
        }, {
          name: 'Artiulation',
          src: require('~/assets/img/corps_humain/pec.jpg'),
          to: '/corps-humains/pec'
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
        default:
          console.log('default')
          break
      }
    }
  }

}
</script>

<style scoped>

</style>
