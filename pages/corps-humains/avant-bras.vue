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
          <span> {{ data.text }} </span> <br>
        </div>
      </div>
    </v-timeline-item>
  </v-timeline>
</template>

<script>
export default {
  name: "Avant-bras",
  layout: 'corps-humain',
  data(){
    return{
      datas:[
        {
          color: 'cyan',
          title: 'Introduction aux avant-bras',
          text: 'Les avant-bras sont la partie de l\'avant-bras située entre le coude et le poignet. Ils sont composés de nombreux muscles, tendons, nerfs et structures anatomiques qui jouent un rôle essentiel dans la flexion, l\'extension et la rotation des poignets et des doigts.\n',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Muscles des avant-bras',
          text: 'Les principaux muscles des avant-bras sont divisés en deux groupes : les muscles fléchisseurs et les muscles extenseurs.\n' +
            '- Les muscles fléchisseurs sont situés à l\'avant de l\'avant-bras et comprennent les muscles du poignet et les muscles des doigts qui sont responsables de la flexion du poignet et des doigts.\n' +
            '- Les muscles extenseurs sont situés à l\'arrière de l\'avant-bras et comprennent les muscles du poignet et les muscles des doigts qui sont responsables de l\'extension du poignet et des doigts.\n'
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Tendons des avant-bras',
          text: 'Les tendons des avant-bras sont les structures qui relient les muscles aux os et permettent la transmission de la force musculaire pour produire des mouvements. Certains des tendons les plus importants des avant-bras comprennent le tendon du biceps brachial, le tendon du triceps brachial, les tendons fléchisseurs et les tendons extenseurs des poignets et des doigts.\n',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Innervation des avant-bras',
          text: 'Les avant-bras sont innervés par plusieurs nerfs, notamment le nerf médian, le nerf ulnaire et le nerf radial. Ces nerfs fournissent la stimulation nerveuse aux muscles des avant-bras, permettant ainsi les mouvements et la sensibilité de la région.\n',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Utilité dans le sport',
          text: 'Les avant-bras jouent un rôle crucial dans de nombreux sports, en particulier ceux qui nécessitent une force de préhension, une coordination des mouvements des mains et des poignets, et une stabilité lors des mouvements. Des sports tels que l\'escalade, le tennis, le golf, l\'haltérophilie et les sports de combat sollicitent spécifiquement les avant-bras.\n',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Risques de blessures possibles',
          text: 'Les blessures courantes des avant-bras peuvent inclure des entorses, des tendinites, des fractures, des déchirures musculaires et des syndromes du canal carpien. Ces blessures peuvent être causées par des traumatismes directs, des mouvements répétitifs, une utilisation excessive ou des déséquilibres musculaires. Les sports de raquette, les sports de contact, les sports de lancer et les sports nécessitant une manipulation fréquente d\'objets peuvent augmenter le risque de blessures aux avant-bras.\n',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Aspect clinique',
          text: 'En cas de blessure aux avant-bras, une évaluation clinique est nécessaire pour déterminer la nature et l\'étendue de la blessure. Cela peut inclure des examens physiques, des radiographies, des échographies ou des IRM pour confirmer le diagnostic. Le traitement peut varier en fonction de la blessure et peut inclure du repos, des soins de rééducation, des médicaments anti-inflammatoires, une immobilisation ou, dans les cas graves, une intervention chirurgicale. Un suivi médical approprié et une rééducation spécialisée sont importants pour une récupération optimale et pour minimiser les complications à long terme.\n',
          // img: require('')
        }
      ]
    }
  }
};
</script>

<style scoped>
span{
  white-space: pre-line;
}
</style>
