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
  name: "Biceps",
  layout: 'corps-humain',
  data(){
    return{
      datas:[
        {
          color: 'cyan',
          title: 'Introduction aux biceps',
          text: 'Les biceps brachii, communément appelés biceps, sont un groupe de muscles situés à l\'avant du bras supérieur. Ils sont composés de deux chefs principaux : le chef long et le chef court. Les biceps jouent un rôle essentiel dans la flexion du coude, la supination de l\'avant-bras et l\'aide à certaines activités de la vie quotidienne.\n',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Muscles biceps brachii',
          text: 'Les muscles biceps brachii comprennent :\n' +
            '- Le chef long : il est le chef le plus externe du biceps et s\'étend depuis l\'omoplate jusqu\'à l\'articulation du coude. Il est principalement responsable de la flexion du coude.\n' +
            '- Le chef court : il est situé à l\'intérieur du chef long et contribue également à la flexion du coude.\n',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Fonctions des biceps',
          text: 'Les biceps sont principalement responsables de la flexion du coude, c\'est-à-dire de la réduction de l\'angle entre l\'avant-bras et le bras. Ils participent également à la supination de l\'avant-bras, qui est la rotation externe de l\'avant-bras permettant la position de la paume vers le haut.\n',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Innervation des biceps',
          text: 'Les biceps sont innervés par le nerf musculo-cutané, qui est une branche du plexus brachial. Ce nerf fournit la stimulation nerveuse aux muscles biceps brachii, permettant leur contraction et leur coordination.\n',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Utilité dans le sport',
          text: 'Les biceps sont importants dans de nombreux sports qui impliquent des mouvements de flexion du coude, tels que l\'haltérophilie, le culturisme, le tennis, le baseball, la gymnastique et le judo. Ils contribuent à la force et à la puissance lors de la manipulation d\'objets, des lancers, des mouvements de préhension et des mouvements de levage.\n',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Risques de blessures possibles',
          text: 'Les blessures courantes des biceps peuvent inclure des déchirures musculaires, des élongations, des tendinites et des douleurs liées à une surutilisation. Ces blessures peuvent être causées par des mouvements brusques, des charges lourdes, une mauvaise technique d\'exercice ou une sollicitation excessive des biceps. Les sports qui nécessitent des mouvements de flexion répétés du coude peuvent augmenter le risque de blessures aux biceps.\n',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Aspect clinique',
          text: 'En cas de blessure aux biceps, une évaluation clinique est nécessaire pour déterminer l\'étendue et la gravité de la blessure. Cela peut inclure un examen physique, des examens d\'imagerie médicale tels que des échographies, des IRM ou des radiographies. Le traitement peut impliquer du repos, des soins de rééducation, des médicaments anti-inflammatoires, une thérapie physique ou, dans certains cas graves, une intervention chirurgicale. Une approche clinique adaptée et une rééducation spécialisée sont essentielles pour une récupération complète et pour minimiser les complications à long terme.\n',
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
