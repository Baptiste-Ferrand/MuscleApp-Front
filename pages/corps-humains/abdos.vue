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
  name: "Abdos",
  layout: 'corps-humain',
  data(){
    return{
      datas:[
        {
          color: 'cyan',
          title: 'Introduction aux abdominaux',
          text: 'Les abdominaux sont un groupe de muscles situés à l\'avant de la paroi abdominale. Ils comprennent les muscles droits de l\'abdomen, les muscles obliques externes et internes, ainsi que les muscles transverses de l\'abdomen. Ces muscles jouent un rôle essentiel dans la posture, le maintien de la stabilité du tronc et la flexion du tronc.',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Muscles des abdominaux',
          text: 'Les muscles principaux des abdominaux sont les suivants :\n' +
            '- Les muscles droits de l\'abdomen : ils sont situés au centre de l\'abdomen et permettent la flexion du tronc.\n' +
            '- Les muscles obliques externes : ils sont situés sur les côtés de l\'abdomen et permettent la flexion latérale et la rotation du tronc.\n' +
            '- Les muscles obliques internes : ils sont situés sous les obliques externes et participent également à la flexion latérale et à la rotation du tronc.\n' +
            '- Les muscles transverses de l\'abdomen : ils sont les plus profonds des muscles abdominaux et aident à la stabilisation du tronc.\n',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Fonctions des abdominaux',
          text: 'Les abdominaux jouent un rôle crucial dans la stabilisation du tronc, le maintien de la posture, la respiration et la flexion du tronc. Ils sont également impliqués dans la protection des organes internes et dans le soutien lors d\'activités physiques telles que la levée d\'objets lourds ou les mouvements de rotation.',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Innervation des abdominaux',
          text: 'Les muscles abdominaux sont innervés par les nerfs thoraciques, en particulier les nerfs intercostaux et les nerfs du plexus lombaire. Ces nerfs fournissent la stimulation nerveuse aux muscles abdominaux, permettant leur contraction et leur coordination.',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Utilité dans le sport',
          text: 'Les abdominaux sont essentiels dans de nombreux sports, car ils fournissent une base solide pour la stabilité du tronc et la génération de puissance. Ils sont impliqués dans les mouvements de rotation, de flexion et de stabilisation du tronc, qui sont nécessaires dans des sports tels que la gymnastique, le golf, la natation, les arts martiaux, le tennis, le cyclisme et bien d\'autres.',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Risques de blessures possibles',
          text: 'Les blessures courantes des abdominaux peuvent inclure des déchirures musculaires, des élongations, des hernies abdominales et des douleurs lombaires. Ces blessures peuvent être causées par des mouvements brusques, des surcharges, des déséquilibres musculaires ou une mauvaise technique d\'exercice. Les sports avec des mouvements de rotation, des impacts directs ou des charges axiales importantes peuvent augmenter le risque de blessures aux abdominaux.',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Aspect clinique',
          text: 'En cas de blessure aux abdominaux, une évaluation clinique est nécessaire pour déterminer l\'étendue et la gravité de la blessure. Cela peut inclure un examen physique, des échographies, des IRM ou d\'autres examens d\'imagerie médicale. Le traitement peut nécessiter du repos, des soins de rééducation, des médicaments anti-inflammatoires, une thérapie physique ou, dans certains cas graves, une intervention chirurgicale. Une approche clinique adaptée et une rééducation spécialisée sont essentielles pour une récupération complète et pour prévenir les complications à long terme.',
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
