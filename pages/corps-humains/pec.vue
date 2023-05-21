<template>
  <v-timeline>
    <v-timeline-item
      v-for="(data, i) in datas"
      :key="i"
      :color="data.color"
      small
    >
      <template #opposite>
        <v-img
          :src="data.img"
          max-width="200px"
        />
      </template>
      <div class="py-4">
        <h2 :class="`headline font-weight-light mb-4 ${data.color}--text`">
          {{ data.title }}
        </h2>
        <div>
          <span class="test"> {{ data.text }} </span> <br>
        </div>
      </div>
    </v-timeline-item>
  </v-timeline>
</template>

<script>
export default {
  name: 'Pec',
  data () {
    return {
      datas: [
        {
          color: 'cyan',
          title: 'Muscle Grand Pectoral',
          text: 'Le muscle grand pectoral est un muscle de la ceinture du membre thoracique. ce muscle est large, triangulaire et puissant, c\'est le plus volumineux du membre thoracique. Le grand pectoral est lié à la paroi antérieure du creux axillaire, dans un plan superficiel' +
         '\nLe grand pectoral est divisé (en fonction des points de vue, générallement cité en 3 partie), en 4 partie: ' +
         '\n- fibres claviculaires' +
         '\n- fibres sternales supérieures' +
         '\n- fibres sternales inférieures' +
         '\n- fibres abdominales.',
          img: require('~/assets/img/corps_humain/pec/2.jpg')
        },
        {
          color: 'green',
          title: 'Terminaison',
          text: 'Les trois faisceaux se terminent en deux, qui s\'insèrent à la face profonde du sillon intertuberculaire, et sur la partie antéro-latérale du grand tubercule de l\'humérus, nous trouvons : ' +
         '\n - le faisceau supérieur qui est formé des fibres claviculaires et de la moitié supérieures des fibres sternales' +
         '\n - le faisceau inférieur qui est formé de la moitié inférieure des fibres sternales et des fibres abdominales.',
          img: require('~/assets/img/corps_humain/pec/1.png')
        },
        {
          color: 'pink',
          title: 'Innervation',
          text: 'Il est innervé par les nerfs pectoraux latéral et médial, issus de l\'anse des pectoraux (Racines C5, C6, (C7), C8 et Th1). ' +
          '\n Les derniers travaux anatomiques ont montré que le grand pectoral était innervé par trois branches nerveuses : ' +
          '\n - une branche supérieure qui innerve le chef claviculaire,' +
          '\n - une branche moyenne qui innerve le chef sternal,' +
          '\n - une branche inférieure qui innerve le chef costal.',
          img: require('~/assets/img/corps_humain/pec/nerf-pectoraux.png')
        },
        {
          color: 'amber',
          title: 'Action',
          text: 'Les actions du muscle grand pectoral sont les suivantes :' +
          '\n - il est principalement adducteur du bras au niveau de l\'épaule,' +
          '\n - Il est aussi rotateur médial (anciennement : interne) de l\'humérus,' +
          '\n - sa partie claviculaire aide à l\'antépulsion (flexion) du bras ainsi qu\'à l\'adduction au-delà de la ligne médiane (ligne passant par l\'axe du corps),' +
          '\n - sa partie sternale, avec les muscles grand dorsal et grand rond, étend l\'humérus fléchi du côté du tronc lors de l\'opposition d\'une résistance,' +
          '\n - il est auxiliaire dans la respiration forcée (augmentation du volume thoracique)',
          img: require('~/assets/img/corps_humain/pec/action.gif')
        },
        {
          color: 'orange',
          title: 'Musculation',
          text: 'Il est courant, à défaut d\'être naturel, de développer le volume, ou la force, des pectoraux (comme de nombreux autres muscles : biceps, triceps, épaules, trapèzes…). exemple le plus courant et le plus simple : les « pompes » (ou push-ups en anglais). Un autre exercice employé couramment par les culturistes est le développé couché avec une barre. Dans cet exercice, qui est aussi un mouvement de la force athlétique, le grand pectoral intervient comme muscle moteur',
          img: require('~/assets/img/corps_humain/pec/bench.gif')
        }
      ]
    }
  }
}
</script>

<style scoped>
.test{
  white-space: pre-wrap
}
</style>
