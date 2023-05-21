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
  name: 'Biceps',
  data () {
    return {
      datas: [
        {
          color: 'cyan',
          title: 'Muscle biceps brachial',
          text: 'Le muscle biceps brachial (ou muscle long fléchisseur de l\'avant-bras) est le muscle fusiforme du bras. Il se situe dans le plan superficiel de la loge brachiale antérieure. Il est composé de deux chefs qui sont : ' +
            '\n \n - Le chef long du muscle biceps brachial est intra-capsulaire de l\'articulation gléno-humérale et se fixe sur le tubercule supraglénoïdal de la scapula1 ainsi que sur la partie haute du labrum glénoïdal de la scapula. ' +
            '\n \n - Le chef court du muscle biceps brachial se fixe sur la partie latérale de l\'apex du processus coracoïde de la scapula par un tendon commun avec le muscle coraco-brachial. ',
          img: require('~/assets/img/corps_humain/biceps/Biceps.png')
        },
        {
          color: 'green',
          title: 'Terminaison / Innervation',
          text: 'Le muscle biceps brachial se termine par un tendon plat qui s’insère sur la partie postérieure de la tubérosité du radius. ' +
            '\n Le tendon libère des expansions aponévrotiques qui recouvrent le fascia antébrachial médial 2, sur la face latérale du radius.' +
            '\n Il forme également une expansion de l\'aponévrose du muscle (lacertus fibrosus) qui cravate les tendons des muscles épicondyliens médiaux s\'achevant sur l\'ulna.' +
            '\n Le muscle biceps brachial est innervé par le nerf musculocutané, branche terminale de la paire de racines rachidiennes cervicales C5-C6 du plexus brachial. Ce nerf est issu du faisceau latéral du plexus brachial. ',
          img: require('~/assets/img/corps_humain/biceps/Radius.jpg')
        },
        {
          color: 'pink',
          title: 'Fonction',
          text: 'Contrairement aux croyances populaires, le « biceps », comme on l\'appelle souvent, n\'est pas que fléchisseur du coude, cette fonction étant assurée conjointement par le muscle brachial (muscle profond) et le muscle brachio-radial. ' +
           '\n En dynamique, il est principalement supinateur, surtout lorsque le coude est fléchi, et ce grâce à son insertion sur la face postérieure de la tubérosité bicipitale du radius. Il est également fléchisseur du coude et de la scapulo-humérale2. ' +
           '\n En statique, par sa longue portion, il participe à la stabilisation de la tête huméral et par sa courte portion à la suspension du bras',
          img: require('~/assets/img/corps_humain/biceps/160px-Animation_triceps_biceps.gif')
        },
        {
          color: 'amber',
          title: 'Aspect clinique',
          text: 'Les principales pathologies du biceps sont la SLAP lesion et la rupture distale du tendon du biceps brachial' +
           '\n SLAP est l\'acronyme de Superior Labrum from Anterior to Posterior. La SLAP lesion est un arrachement du bourrelet glénoïdien supérieur. Elle se produit le plus souvent lors des mouvements de traction dans les sports de lancer' +
           '\n La rupture distale du tendon du biceps brachial a lieu le plus souvent chez le travailleur de force ou le sportif lors de l\'utilisation de la flexion du coude contre une résistance' +
           '\n Elle se manifeste par une douleur brutale souvent accompagnée par une sensation de claquage "en coup de fouet". La palpation du pli du coude entraîne des douleurs,',
          img: require('~/assets/img/corps_humain/biceps/SLAP-tear-shoulder.jpg')
        },
        {
          color: 'orange',
          title: 'Musculation',
          text: 'Il est courant de développer le volume ou la force du biceps à l\'aide d\'exercices de musculation, dont un exemple peut être la flexion du coude contre une charge.' +
           '\n Le biceps brachial intervient comme muscle synergique dans l\'exercice du développé couché' +
           '\n En bodybuilding, on distingue couramment deux types de biceps: les biceps court et les biceps long. Cette distinction est purement esthétique et il n y a aucune différence de fonctionnement et d’efficacité entre les deux variantes. Cependant, un biceps dit court aura un tendon plus long, ce qui est plus propice aux blessures',
          img: require('~/assets/img/corps_humain/biceps/biceps_court_vs_long.png')
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
