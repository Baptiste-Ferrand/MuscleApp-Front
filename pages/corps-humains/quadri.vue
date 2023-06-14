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
  name: "Pec",
  layout: 'corps-humain',
  data(){
    return{
      datas:[
        {
          color: 'cyan',
          title: 'Introduction aux quadriceps',
          text: 'Les quadriceps femoris, communément appelés quadriceps, sont un groupe de muscles situés à l\'avant de la cuisse. Ils sont composés de quatre chefs principaux : le vaste externe, le vaste intermédiaire, le vaste interne et le droit fémoral. Les quadriceps jouent un rôle essentiel dans l\'extension du genou et la stabilisation de l\'articulation de la hanche.\n',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Muscles quadriceps femoris',
          text: 'Les muscles quadriceps femoris comprennent :\n' +
            '- Le vaste externe : il est le chef le plus externe du quadriceps et est situé sur la partie latérale de la cuisse. Il est principalement responsable de l\'extension du genou.\n' +
            '- Le vaste intermédiaire : situé au milieu de la cuisse, il contribue également à l\'extension du genou.\n' +
            '- Le vaste interne : situé sur la partie interne de la cuisse, il participe également à l\'extension du genou.\n' +
            '- Le droit fémoral : situé sur la partie antérieure de la cuisse, il joue un rôle important dans l\'extension du genou et la flexion de la hanche.\n',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Fonctions des quadriceps',
          text: 'Les quadriceps sont principalement responsables de l\'extension du genou, c\'est-à-dire de l\'augmentation de l\'angle entre la jambe et la cuisse. Ils jouent également un rôle dans la stabilité de l\'articulation de la hanche lors des activités nécessitant une force et une stabilité dans les mouvements des membres inférieurs.\n',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Innervation des quadriceps',
          text: 'Les quadriceps sont innervés par le nerf fémoral, qui est une branche du plexus lombaire. Ce nerf fournit la stimulation nerveuse aux muscles quadriceps femoris, permettant leur contraction et leur coordination.\n',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Utilité dans le sport',
          text: 'Les quadriceps sont d\'une importance cruciale dans de nombreux sports qui impliquent des mouvements des membres inférieurs, tels que la course à pied, le saut, le cyclisme, le football, le basketball et l\'haltérophilie. Ils contribuent à la force et à la puissance lors des mouvements d\'extension du genou et jouent un rôle dans la stabilité et le contrôle du mouvement lors des activités sportives.\n',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Risques de blessures possibles',
          text: 'Les blessures courantes des quadriceps peuvent inclure des déchirures musculaires, des élongations, des tendinites et des douleurs liées à une surutilisation. Ces blessures peuvent être causées par des mouvements brusques, des charges lourdes, des déséquilibres musculaires, une mauvaise technique d\'exercice ou une sollicitation excessive des quadriceps. Certains sports, comme la course à pied ou le saut, peuvent augmenter le risque de blessures aux quadriceps.\n',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Aspect clinique',
          text: 'En cas de blessure aux quadriceps, une évaluation clinique est nécessaire pour déterminer l\'étendue et la gravité de la blessure. Cela peut inclure un examen physique, des examens d\'imagerie médicale tels que des échographies, des IRM ou des radiographies. Le traitement peut impliquer du repos, des soins de rééducation, des médicaments anti-inflammatoires, une thérapie physique ou, dans certains cas graves, une intervention chirurgicale. Une approche clinique adaptée et une rééducation spécialisée sont essentielles pour une récupération complète et pour minimiser les complications à long terme.\n',
          // img: require('')
        },
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
