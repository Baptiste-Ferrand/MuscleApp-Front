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
  name: 'Jambes',
  data () {
    return {
      datas: [
        {
          color: 'cyan',
          title: 'Muscle ischio-jambier',
          text: 'Un muscle ischio-jambier appartient à un groupe musculaire de la cuisse permettant l\'extension de la hanche et la flexion du genou. Ce groupe rassemble des muscles polyarticulaires qui vont de la hanche jusqu’à l’arrière du tibia et de la fibula ' +
          '\n Ces muscles correspondent aux muscles de la loge postérieure de la cuisse.  ' +
          '\n Ce groupe se compose de trois muscles :  ' +
          '\n - muscle biceps fémoral ' +
          '\n - muscle semi-tendineux  ' +
          '\n - muscle semi-membraneux. ',
          img: require('~/assets/img/corps_humain/ishio/ishio.png')
        },
        {
          color: 'green',
          title: 'Insertions des ischio-jambiers',
          text: 'Muscle biceps fémoral est composé par deux chefs. Le chef long (caput longum) naît par un tendon sur la face postérieure de la tubérosité ischiatique, Le chef court, quant à lui, naît par des fibres musculaires sur la moitié distale de la lèvre latérale de la ligne âpre' +
           '\nLes deux chefs se rejoignent pour se fixer sur la tête de la fibula et par des expansions sur le condyle latéral du tibia' +
           '\nMuscle semi-tendineux, le plus interne au niveau du creux poplité. Il naît sur la tubérosité ischiatique pour se terminer sur la face supérieure et médiale du tibia. Il appartient au groupe de la patte d\'oie' +
           '\nMuscle semi-membraneux, saille beaucoup moins que le demi tendineux, et se trouve en dehors de lui, en arrière et en dehors du condyle médial.',
          img: require('~/assets/img/corps_humain/ishio/shema_ishio.png')
        },
        {
          color: 'pink',
          title: 'Innervation / Pathologies',
          text: 'Tous ces muscles sont innervés par le nerf ischiatique . Ses racines métamériques sont L4-L5 et S1-S2-S3. ' +
           '\nCe groupe musculaire est l\'un des plus touchés par les accidents musculaires des sportifs, dont le plus grave est la déchirure musculaire. Une étude scandinave a par exemple montré que les ischio-jambiers sont impliqués, dans cette région, dans 11 % des blessures dans la course à pied,',
          img: require('~/assets/img/corps_humain/ishio/nerf.jpg')
        },
        {
          color: 'amber',
          title: 'Fonction',
          text: 'Les muscles ischio-jambiers sont composés de plusieurs parties qui ont pour action principale d\'entrainer le genou en flexion et le fémur en extension si l\'os coxal est un point fixe :' +
         '\n- Muscle biceps fémoral : il permet la flexion de la jambe et la rotation latérale de la jambe fléchie. Le chef long participe à l\'extension de la hanche.' +
         '\n- Muscle semi-tendineux : il permet la flexion de la jambe. De plus, lorsque la jambe est fléchie, il est rotateur médial de la jambe et extenseur de la hanche.' +
         '\n- Muscle semi-membraneux : ses fonctions sont identiques à celles du muscle semi-tendineux. De plus, il est tenseur de la capsule articulaire (par le ligament poplité oblique).',
          img: require('~/assets/img/corps_humain/ishio/Femur.png')
        },
        {
          color: 'orange',
          title: 'Musculation',
          text: 'Les ischio-jambiers interviennent comme muscles moteurs ou synergiques dans l\'exercice du soulevé de terre. Ils sont également moteurs dans le mouvement de flexion sur jambes avec le squat',
          img: require('~/assets/img/corps_humain/ishio/squat.jpg')
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
