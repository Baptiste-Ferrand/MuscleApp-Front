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
  name: "Epaule",
  layout: 'corps-humain',
  data(){
    return{
      datas:[
        {
          color: 'cyan',
          title: 'Introduction à l\'épaule humaine',
          text: 'L\'épaule est une articulation synoviale de type sphéroïde qui permet une grande mobilité et une vaste gamme de mouvements. Elle est composée de l\'articulation glénohumérale entre la tête de l\'humérus et la cavité glénoïde de la scapula. Elle est soutenue par plusieurs structures, notamment l\'articulation acromioclaviculaire entre la clavicule et l\'acromion de la scapula, ainsi que l\'articulation scapulothoracique entre la scapula et la paroi thoracique.',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Muscles de l\'épaule',
          text: 'Les muscles de l\'épaule comprennent :\n' +
                 '\n1. Deltoïde : Il se compose de trois faisceaux (antérieur, moyen et postérieur) et est responsable de l\'élévation et de l\'abduction du bras.' +
                 '\n2. Muscles de la coiffe des rotateurs : Ils comprennent le supra-épineux, l\'infra-épineux, le petit rond et le subscapulaire. Ces muscles jouent un rôle clé dans la stabilisation de l\'articulation glénohumérale et la rotation externe et interne du bras.' +
                 '\n3. Trapèze : Il est subdivisé en trapèze supérieur, moyen et inférieur et contribue à la rotation de l\'omoplate et à l\'élévation de l\'épaule.'+
                 '\n4. Grand pectoral : Ce muscle situé sur la partie antérieure de la poitrine aide à fléchir, adducter et faire tourner le bras vers l\'intérieur.'
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Tendons de l\'épaule',
          text: 'Les tendons jouent un rôle crucial dans la stabilité et le mouvement de l\'épaule. Les principaux tendons de la coiffe des rotateurs sont le tendon du supra-épineux, du sous-scapulaire, de l\'infra-épineux et du petit rond. Ils s\'attachent à l\'humérus et contribuent à la stabilisation de l\'articulation glénohumérale lors des mouvements du bras.',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Innervation de l\'épaule',
          text: 'L\'épaule est innervée par plusieurs nerfs, notamment :\n' +
            '1. Nerf axillaire (branche du plexus brachial) : Il innerve le muscle deltoïde et fournit la sensibilité cutanée à la peau de l\'épaule et de la partie supérieure du bras.\n' +
            '2. Nerf supra-scapulaire (branche du plexus brachial) : Il innerve les muscles supra-épineux et infra-épineux, contribuant à la rotation externe et à l\'abduction de l\'épaule.\n' +
            '3. Nerf subscapulaire supérieur et nerf subscapulaire inférieur (branches du plexus brachial) : Ils innervent le muscle subscapulaire, qui participe à la rotation interne de l\'épaule.\n',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Utilité dans le sport',
          text: 'L\'épaule est essentielle dans de nombreux sports, notamment ceux qui exigent des mouvements de lancer, de frappe ou de projection. Par exemple, dans le baseball, le lancer de javelot, le tennis ou la natation, l\'épaule est sollicitée pour générer la puissance, la stabilité et la précision nécessaires aux mouvements sportifs spécifiques.',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Risques de blessures possibles',
          text: 'Les blessures de l\'épaule peuvent inclure des entorses, des luxations, des tendinites et des déchirures des tendons de la coiffe des rotateurs. Ces blessures peuvent être causées par une utilisation excessive, des traumatismes directs, des mouvements répétitifs ou des déséquilibres musculaires. Les sports à forte intensité et à mouvements rapides augmentent le risque de blessure à l\'épaule.',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Aspect clinique',
          text: 'En cas de blessure à l\'épaule, une évaluation clinique approfondie est nécessaire. Cela peut inclure des tests spécifiques tels que le test de Neer, le test de Hawkins-Kennedy et le test de Jobe pour évaluer la présence de lésions de la coiffe des rotateurs. Des examens complémentaires, tels que des radiographies, des échographies ou des IRM, peuvent être utilisés pour confirmer le diagnostic et évaluer l\'étendue des lésions. Le traitement peut impliquer des approches conservatrices (repos, physiothérapie, médicaments) ou, dans les cas graves, une intervention chirurgicale pour réparer les structures lésées. Un suivi médical et une rééducation appropriée sont importants pour la récupération optimale de l\'épaule blessée.',
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
