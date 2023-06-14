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
          title: 'Introduction aux pectoraux',
          text: 'Les pectoraux, également appelés muscles pectoraux, sont un groupe de muscles situés à l\'avant de la poitrine. Ils comprennent le grand pectoral (pectoralis major) et le petit pectoral (pectoralis minor). Ces muscles jouent un rôle essentiel dans les mouvements des bras, la stabilisation de l\'épaule et la posture.\n',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Muscle Grand Pectoral',
          text: 'Les muscles pectoraux comprennent :\n' +
            '\n' +
            'Le grand pectoral (pectoralis major) : il est le plus grand muscle de la poitrine et est responsable de l\'adduction (rapprochement) de l\'épaule, de la flexion et de la rotation interne du bras.\n' +
            'Le petit pectoral (pectoralis minor) : situé en dessous du grand pectoral, il est responsable de la stabilisation de l\'omoplate en la tirant vers l\'avant et vers le bas.\n',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Fonctions des pectoraux',
          text: 'Les pectoraux jouent un rôle crucial dans de nombreux mouvements des bras, tels que le mouvement d\'adduction (rapprochement) de l\'épaule, la flexion du bras et la rotation interne du bras. Ils contribuent également à la stabilité de l\'épaule en maintenant une bonne posture et en soutenant les mouvements des membres supérieurs.\n',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Innervation des pectoraux',
          text: 'Les muscles pectoraux sont innervés par le nerf pectoral latéral, qui est une branche du plexus brachial. Ce nerf fournit la stimulation nerveuse aux muscles pectoraux, permettant leur contraction et leur coordination.\n',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Utilité dans le sport',
          text: 'Les pectoraux sont importants dans de nombreux sports qui impliquent des mouvements des membres supérieurs, tels que l\'haltérophilie, la natation, le tennis, le basket-ball et la gymnastique. Ils contribuent à la force, à la puissance et à la stabilité lors des mouvements des bras.\n',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Risques de blessures possibles',
          text: 'Les blessures courantes des pectoraux peuvent inclure des déchirures musculaires, des élongations, des tendinites et des douleurs liées à une surutilisation. Ces blessures peuvent être causées par des traumatismes directs, des mouvements brusques, une surcharge, une mauvaise technique d\'exercice ou un déséquilibre musculaire. Certains sports, comme l\'haltérophilie et les sports de contact, peuvent augmenter le risque de blessures aux pectoraux.\n',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Aspect clinique',
          text: 'En cas de blessure aux pectoraux, une évaluation clinique est nécessaire pour déterminer l\'étendue et la gravité de la blessure. Cela peut inclure un examen physique, des examens d\'imagerie médicale tels que des radiographies, des échographies ou des IRM. Le traitement peut impliquer du repos, des soins de rééducation, des médicaments anti-inflammatoires, une thérapie physique ou, dans certains cas graves, une intervention chirurgicale. Une approche clinique adaptée et une rééducation spécialisée sont essentielles pour une récupération complète et pour minimiser les complications à long terme.\n',
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
