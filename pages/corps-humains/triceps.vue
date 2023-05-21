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
  name: 'Triceps',
  data () {
    return {
      datas: [
        {
          color: 'cyan',
          title: 'Muscle Triceps Brachial',
          text: 'Le muscle triceps brachial est un muscle postérieur du bras. C\'est le seul muscle de la loge brachiale postérieure. ' +
           '\nIl se divise en trois chefs : ' +
           '\n- Le chef latéral du triceps brachial se fixe au niveau de la face postérieure de la moitié proximale de l\'humérus au-dessus du sillon du nerf radial. ' +
           '\n- Le chef médial du triceps brachial se fixe au niveau des faces postérieure et médiale de la moitié distale de l\'humérus au-dessous du sillon du nerf radial.' +
           '\nIl se fixe également sur la face postérieure des septums intermusculaires latéral et médial. ' +
           '\n- Le long chef du triceps brachial se fixe sur le tubercule infraglénoïdal de la scapula et sur le labrum glénoïdal. ',
          img: require('~/assets/img/corps_humain/triceps/triceps-exercice-musculation_480x480.jpg')
        },
        {
          color: 'green',
          title: 'Trajet / Terminaison',
          text: 'Les trois chefs du muscle se dirigent vers le bas et se rejoignent au ventre du muscle.' +
           '\nLe muscle triceps brachial se termine par une lame tendineuse aplatie d\'avant en arrière qui s\'insère sur la face supérieure de l\'olécrane.' +
           '\nLes fibres musculaires inférieures du chef médial s\'insère sur les faces latérale et médiale de l\'olécrane.',
          img: require('~/assets/img/corps_humain/triceps/Olécrâne.jpg')
        },
        {
          color: 'pink',
          title: 'Innervation / Vascularisation',
          text: 'Le muscle triceps brachial est innervé par le nerf radial (C7 et C8)' +
           '\n Le muscle triceps brachial est irrigué par l\'artère brachiale profonde',
          img: require('~/assets/img/corps_humain/triceps/artere_profond.png')
        },
        {
          color: 'amber',
          title: 'Action',
          text: 'Les actions du muscle grand pectoral sont les suivantes :' +
          '\n- Le muscle triceps brachial permet l\'extension du coude et la rétropulsion de l\'épaule.' +
          '\n- Les chefs médial et latéral sont des extenseurs du coude' +
          '\n- Le chef long est extenseur du coude en synergie avec les chefs médial et latéral. Il est également extenseur du bras en synergie avec la portion postérieure des muscles deltoïde, grand rond et grand dorsal. De plus, le chef long limite le décentrage de la tête humérale. ',
          img: require('~/assets/img/corps_humain/triceps/260px-Triceps_brachii.png')
        },
        {
          color: 'orange',
          title: 'Musculation',
          text: 'Les exercices les plus efficaces pour les triceps sont les extensions des avant-bras à la barre, couché sur un banc, le développé couché prise serrée ou encore les dips. ',
          img: require('~/assets/img/corps_humain/triceps/Dips.png')
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
