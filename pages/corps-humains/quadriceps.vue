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
  name: 'Quadriceps',
  data () {
    return {
      datas: [
        {
          color: 'cyan',
          title: 'Muscle quadriceps fémoral',
          text: 'Le muscle quadriceps fémoral est le muscle le plus volumineux du corps humain. C\'est lui qui supporte en grande partie le poids du corps et permet de se déplacer' +
          '\n Il se situe dans la loge antérieure de la cuisse. Son nom vient de sa structure et de ses quatre ventres musculaires. Il est attaché à la patella.   ' +
          '\nCe groupe se compose de deux grosse insertions décomposer en 4 muscles :  ' +
          '\n- Insertions hautes avec le muscle droit fémoral, le vaste latéral, vaste médial et vaste intermédiaire ' +
          '\n- Insertions basses avec les mêmes nom droit fémoral vaste latéral etc ',
          img: require('~/assets/img/corps_humain/quadriceps/Quadriceps_full.png')
        },
        {
          color: 'green',
          title: 'Insertions du quadriceps',
          text: 'Insertions haute : Muscle droit fémoral : épine iliaque antéro-inférieure, sillon supra-acétabulaire et capsule articulaire coxofémorale\n' +
            'Muscle vaste latéral : base du grand trochanter et sur la ligne âpre\n' +
            'Muscle vaste médial : diaphyse du fémur \n' +
            'Muscle vaste intermédiaire : face antérieure de la diaphyse fémorale' +
           '\n \n Insertions basses :  Muscle droit fémoral : suit le tendon patellaire jusqu\'à la face antérieure du tibia.\n' +
            'Muscle vaste latéral : face supérieure de la patella.\n' +
            'Muscle vaste médial : face supérieure de la patella.\n' +
            'Muscle vaste intermédiaire : face supérieure de la patella.',
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
          '\n Fléchisseur de la cuisse sur le bassin (articulation de la hanche) par le droit fémoral' +
          '\n Antéverseur du bassin et crée le recurvatum du genou si membre fixé.',
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
