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
  name: 'Mollet',
  data () {
    return {
      datas: [
        {
          color: 'cyan',
          title: 'Muscle Mollet',
          text: 'En anatomie humaine, le mollet désigne un ensemble de muscles situés entre le jarret (ou creux poplité) et le tendon d\'Achille. Sa longueur et donc celle du tendon d\'Achille sont variables selon le profil génétique de l\'individu.' +
           '\nAinsi les coureurs de haut niveau ont la particularité d\'avoir des mollets courts, voire très courts, et un long tendon d\'Achille ' +
           '\nCe groupe se compose de deux grosse insertions décomposer en 4 muscles ' +
           '\nSur le plan esthétique, c\'est lui qui donne son relief à la face postérieure de la jambe. Durant la marche le mollet joue un rôle circulatoire important, la contraction des muscles jouant un rôle de pompe sur le flux sanguin. ',
          img: require('~/assets/img/corps_humain/molet/extremity_muscles.jpg')
        },
        {
          color: 'green',
          title: 'Anatomie / Étymologie',
          text: 'Le muscle triceps sural en arrière (muscle gastrocnémien latéral, muscle gastrocnémien médial et soléaire) et le groupe des muscles péroniers latéraux en dehors (long fibulaire et court fibulaire) constituent l\'essentiel du volume du mollet, qui livre passage dans sa profondeur à l\'artère tibiale postérieure et à l\'artère péronière.' +
           '\nÉtymologiquement, le mollet vient de mol (mou). L\'adjectif « sural », du latin sura (mollet), désigne ce qui est relatif au mollet. ',
          img: require('~/assets/img/corps_humain/quadriceps/Quadriceps.jpg')
        },
        {
          color: 'pink',
          title: 'Innervation / Pathologies',
          text: 'Par les différentes branches du nerf du quadriceps, lui-même branche terminale motrice pure du nerf fémoral, issu du plexus lombaire. ' +
           '\nDéchirure musculaire' +
           '\nUne amyotrophie du vaste médial peut entraîner un syndrome rotulien ',
          img: require('~/assets/img/corps_humain/quadriceps/Lumbar_plexus.svg.png')
        },
        {
          color: 'amber',
          title: 'Fonction',
          text: 'Extenseur de la jambe sur la cuisse (articulation du genou) si tronc fixé' +
           '\nFléchisseur de la cuisse sur le bassin (articulation de la hanche) par le droit fémoral' +
           '\nAntéverseur du bassin et crée le recurvatum du genou si membre fixé.',
          img: require('~/assets/img/corps_humain/quadriceps/Quadriceps_3D.gif')
        },
        {
          color: 'orange',
          title: 'Musculation',
          text: 'Les quadriceps interviennent comme muscles moteurs ou synergiques dans l\'exercice du soulevé de terre, de la presse à cuisses et de la flexion sur jambes comme le squat',
          img: require('~/assets/img/corps_humain/quadriceps/souleve-de-terre.gif')
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
