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
  name: "Mollet",
  layout: 'corps-humain',
  data(){
    return{
      datas:[
        {
          color: 'cyan',
          title: 'Introduction aux mollets',
          text: 'Les mollets sont la partie postérieure de la jambe située entre le genou et la cheville. Ils sont principalement composés de muscles, de tendons et de nerfs qui jouent un rôle essentiel dans la mobilité et la stabilité de la cheville.',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Muscles des mollets',
          text: 'Les muscles principaux des mollets sont le gastrocnémien et le soléaire, qui forment ensemble le triceps sural. Ces muscles sont responsables de la flexion plantaire de la cheville, c\'est-à-dire de pointer le pied vers le bas.',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Innervation des mollets',
          text: 'Les mollets sont innervés par le nerf tibial, qui est une branche du nerf sciatique. Le nerf tibial fournit la stimulation nerveuse aux muscles du mollet, leur permettant de se contracter et de produire des mouvements.\n',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Utilité dans le sport',
          text: 'Les mollets sont extrêmement importants dans de nombreux sports, en particulier ceux qui impliquent des sauts, des sprints et des mouvements rapides des membres inférieurs. Par exemple, dans l\'athlétisme, le basketball, le saut en longueur et les sports de saut en hauteur, les mollets sont sollicités pour générer de la puissance et de la propulsion lors des mouvements.\n',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Risques de blessures possibles',
          text: 'Les blessures courantes des mollets comprennent les déchirures musculaires (élongations ou déchirures du muscle du mollet), les tendinites du tendon d\'Achille, les crampes musculaires et les fractures de stress. Ces blessures peuvent être causées par des mouvements brusques, des traumatismes directs, une surutilisation, des déséquilibres musculaires ou un échauffement insuffisant. Les sports qui impliquent des changements de direction rapides, des sauts répétés ou une forte demande sur les mollets augmentent le risque de blessures.\n',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Aspect clinique',
          text: 'En cas de blessure aux mollets, une évaluation clinique est nécessaire pour déterminer l\'étendue de la blessure. Cela peut inclure des examens physiques, des échographies, des IRM ou des radiographies pour confirmer le diagnostic. Le traitement peut impliquer du repos, de la glace, de la compression, de l\'élévation (technique RICE), des médicaments anti-inflammatoires, une physiothérapie ou, dans les cas graves, une intervention chirurgicale. Un suivi médical et une rééducation adéquate sont importants pour assurer une récupération complète et minimiser les risques de récidive des blessures aux mollets.',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Aspect clinique',
          text: 'En cas de blessure aux mollets, une évaluation clinique est nécessaire pour déterminer l\'étendue de la blessure. Cela peut inclure des examens physiques, des échographies, des IRM ou des radiographies pour confirmer le diagnostic. Le traitement peut impliquer du repos, de la glace, de la compression, de l\'élévation (technique RICE), des médicaments anti-inflammatoires, une physiothérapie ou, dans les cas graves, une intervention chirurgicale. Un suivi médical et une rééducation adéquate sont importants pour assurer une récupération complète et minimiser les risques de récidive des blessures aux mollets.\n',
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
