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
          {{ data.part1 }}
        </h2>
        <div>
          <span> {{ data.subpart1 }} </span> <br>
          <span> {{ data.subpart1_2 }} </span> <br>
          <span> {{ data.subpart1_3 }} <br>
            {{ data.subpart1_4 }} <br>
            {{ data.subpart1_5 }} <br>
            {{ data.subpart1_6 }} <br>
          </span> <br>
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
          part1: 'Muscle Grand Pectoral',
          subpart1: 'Le muscle grand pectoral est un muscle de la ceinture du membre thoracique. ce muscle est large, triangulaire et puissant, c\'est le plus volumineux du membre thoracique. Le grand pectoral est lié à la paroi antérieure du creux axillaire, dans un plan superficiel',
          subpart1_2: 'Le grand pectoral est divisé (en fonction des points de vue, générallement cité en 3 partie), en 4 partie: ',
          subpart1_3: '- fibres claviculaires',
          subpart1_4: '- fibres sternales supérieures',
          subpart1_5: '- fibres sternales inférieures',
          subpart1_6: '- fibres abdominales.',
          img: require('~/assets/img/corps_humain/pec/2.jpg')
        },
        {
          color: 'green',
          part1: 'Terminaison',
          subpart1: 'Les trois faisceaux se terminent en deux, qui s\'insèrent à la face profonde du sillon intertuberculaire, et sur la partie antéro-latérale du grand tubercule de l\'humérus, nous trouvons : ',
          subpart1_2: '- le faisceau supérieur qui est formé des fibres claviculaires et de la moitié supérieures des fibres sternales',
          subpart1_3: '- le faisceau inférieur qui est formé de la moitié inférieure des fibres sternales et des fibres abdominales.',
          img: require('~/assets/img/corps_humain/pec/1.png')
        },
        {
          color: 'pink',
          part1: 'Innervation',
          subpart1: 'Il est innervé par les nerfs pectoraux latéral et médial, issus de l\'anse des pectoraux (Racines C5, C6, (C7), C8 et Th1). ',
          subpart1_2: 'Les derniers travaux anatomiques ont montré que le grand pectoral était innervé par trois branches nerveuses : ',
          subpart1_3: '- une branche supérieure qui innerve le chef claviculaire,',
          subpart1_4: '- une branche moyenne qui innerve le chef sternal,',
          subpart1_5: '- une branche inférieure qui innerve le chef costal.'
        },
        {
          color: 'amber',
          part1: 'Action',
          subpart1: 'Les actions du muscle grand pectoral sont les suivantes :',
          subpart1_2: '- il est principalement adducteur du bras au niveau de l\'épaule,',
          subpart1_3: '- Il est aussi rotateur médial (anciennement : interne) de l\'humérus,',
          subpart1_4: '- sa partie claviculaire aide à l\'antépulsion (flexion) du bras ainsi qu\'à l\'adduction au-delà de la ligne médiane (ligne passant par l\'axe du corps),',
          subpart1_5: '- sa partie sternale, avec les muscles grand dorsal et grand rond, étend l\'humérus fléchi du côté du tronc lors de l\'opposition d\'une résistance,',
          subpart1_6: '- il est auxiliaire dans la respiration forcée (augmentation du volume thoracique)'
        },
        {
          color: 'orange',
          part1: 'Musculation',
          subpart1: 'Il est courant, à défaut d\'être naturel, de développer le volume, ou la force, des pectoraux (comme de nombreux autres muscles : biceps, triceps, épaules, trapèzes…). exemple le plus courant et le plus simple : les « pompes » (ou push-ups en anglais). Un autre exercice employé couramment par les culturistes est le développé couché avec une barre. Dans cet exercice, qui est aussi un mouvement de la force athlétique, le grand pectoral intervient comme muscle moteur'
        }
      ]
    }
  }
}
</script>

<style scoped>

</style>
