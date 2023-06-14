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
  name: "Triceps",
  layout: 'corps-humain',
  data(){
    return{
      datas:[
        {
          color: 'cyan',
          title: 'Introduction aux triceps',
          text: 'Les triceps brachii, communément appelés triceps, sont un groupe de muscles situés à l\'arrière du bras supérieur. Ils sont composés de trois chefs principaux : le chef long, le chef latéral et le chef médial. Les triceps jouent un rôle essentiel dans l\'extension du coude et dans la stabilisation de l\'articulation de l\'épaule.\n',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Muscles triceps brachii',
          text: 'Les muscles triceps brachii comprennent :\n' +
            '- Le chef long : il est le chef le plus externe du triceps et s\'étend depuis l\'omoplate jusqu\'à l\'articulation du coude. Il est principalement responsable de l\'extension du coude.\n' +
            '- Le chef latéral : situé sur le côté externe du bras, il contribue également à l\'extension du coude.\n' +
            '- Le chef médial : situé sur le côté interne du bras, il participe également à l\'extension du coude.\n',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Fonctions des triceps',
          text: 'Les triceps sont principalement responsables de l\'extension du coude, c\'est-à-dire de l\'augmentation de l\'angle entre l\'avant-bras et le bras. Ils jouent également un rôle dans la stabilisation de l\'articulation de l\'épaule lors d\'activités nécessitant une force et une stabilité dans les mouvements des bras.\n',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Innervation des triceps',
          text: 'Les triceps sont innervés par le nerf radial, qui est une branche du plexus brachial. Ce nerf fournit la stimulation nerveuse aux muscles triceps brachii, permettant leur contraction et leur coordination.\n',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Utilité dans le sport',
          text: 'Les triceps sont importants dans de nombreux sports qui impliquent des mouvements d\'extension du coude, tels que l\'haltérophilie, le culturisme, le tennis, la natation, le basketball et les sports de combat. Ils contribuent à la force et à la puissance lors des mouvements d\'extension du coude et jouent un rôle dans les mouvements de poussée et de lancer.\n',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Risques de blessures possibles',
          text: 'Les blessures courantes des triceps peuvent inclure des déchirures musculaires, des élongations, des tendinites et des douleurs liées à une surutilisation. Ces blessures peuvent être causées par des mouvements brusques, des charges lourdes, une mauvaise technique d\'exercice ou une sollicitation excessive des triceps. Certains sports, comme l\'haltérophilie, le culturisme ou les sports de combat, peuvent augmenter le risque de blessures aux triceps.\n',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Aspect clinique',
          text: 'En cas de blessure aux triceps, une évaluation clinique est nécessaire pour déterminer l\'étendue et la gravité de la blessure. Cela peut inclure un examen physique, des examens d\'imagerie médicale tels que des échographies, des IRM ou des radiographies. Le traitement peut impliquer du repos, des soins de rééducation, des médicaments anti-inflammatoires, une thérapie physique ou, dans certains cas graves, une intervention chirurgicale. Une approche clinique adaptée et une rééducation spécialisée sont essentielles pour une récupération complète et pour minimiser les complications à long terme.\n',
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
