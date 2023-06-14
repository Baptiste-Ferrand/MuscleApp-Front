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
          title: 'Introduction aux ischio-jambiers',
          text: 'Les ischio-jambiers sont un groupe de muscles situés à l\'arrière de la cuisse. Ils comprennent trois muscles principaux : le muscle biceps fémoral, le muscle semi-tendineux et le muscle semi-membraneux. Les ischio-jambiers jouent un rôle essentiel dans la flexion du genou, l\'extension de la hanche et la stabilisation du bassin.\n',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Muscles ischio-jambiers',
          text: 'Les muscles ischio-jambiers comprennent :\n' +
            '- Le muscle biceps fémoral : il est situé sur la partie externe de la cuisse. Il est composé de deux faisceaux, le faisceau long et le faisceau court. Le muscle biceps fémoral contribue à la flexion du genou et à l\'extension de la hanche.\n' +
            '- Le muscle semi-tendineux : il est situé à l\'intérieur de la cuisse, médialement par rapport au muscle biceps fémoral. Il participe à la flexion du genou et à l\'extension de la hanche.\n' +
            '- Le muscle semi-membraneux : il est également situé à l\'intérieur de la cuisse, médialement par rapport au muscle semi-tendineux. Il joue un rôle dans la flexion du genou, l\'extension de la hanche et la stabilisation du bassin.\n',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Fonctions des ischio-jambiers',
          text: 'Les ischio-jambiers sont principalement responsables de la flexion du genou, c\'est-à-dire de la réduction de l\'angle entre la jambe et la cuisse. Ils jouent également un rôle dans l\'extension de la hanche, la rotation interne du genou et la stabilisation du bassin lors des mouvements des membres inférieurs.\n',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Innervation des ischio-jambiers',
          text: 'Les ischio-jambiers sont innervés par le nerf sciatique, qui est le nerf le plus long et le plus épais du corps humain. Le nerf sciatique fournit la stimulation nerveuse aux muscles ischio-jambiers, permettant leur contraction et leur coordination.\n',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Utilité dans le sport',
          text: 'Les ischio-jambiers sont d\'une grande importance dans de nombreux sports qui impliquent des mouvements des membres inférieurs, tels que la course à pied, le saut, le football, le rugby, l\'athlétisme et le sprint. Ils contribuent à la force et à la puissance lors des mouvements de flexion du genou, de l\'extension de la hanche et de la stabilisation du bassin.\n',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Risques de blessures possibles',
          text: 'Les blessures courantes des ischio-jambiers comprennent les déchirures musculaires, les élongations et les tendinites. Ces blessures peuvent être causées par des mouvements brusques, des étirements excessifs, une mauvaise technique d\'exercice, une faiblesse musculaire ouune surutilisation des ischio-jambiers. Certains sports, comme la course à pied ou le sprint, peuvent augmenter le risque de blessures aux ischio-jambiers.\n',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Aspect clinique',
          text: 'En cas de blessure aux ischio-jambiers, une évaluation clinique est nécessaire pour déterminer l\'étendue et la gravité de la blessure. Cela peut inclure un examen physique, des examens d\'imagerie médicale tels que des échographies ou des IRM. Le traitement peut impliquer du repos, des soins de rééducation, des médicaments anti-inflammatoires, une thérapie physique ou, dans certains cas graves, une intervention chirurgicale. Une approche clinique adaptée et une rééducation spécialisée sont essentielles pour une récupération complète et pour minimiser les complications à long terme.\n',
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
