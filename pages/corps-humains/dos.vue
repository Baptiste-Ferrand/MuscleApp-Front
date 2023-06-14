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
  name: "Dos",
  layout: 'corps-humain',
  data(){
    return{
      datas:[
        {
          color: 'cyan',
          title: 'Introduction au dos',
          text: 'Le dos est la région postérieure du tronc humain et s\'étend de la base du crâne jusqu\'au bassin. Il se compose de la colonne vertébrale, des muscles, des ligaments et des nerfs qui lui sont associés.',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Muscles du dos',
          text: 'Les muscles du dos sont divisés en plusieurs groupes :\n' +
            '1. Muscles superficiels : Le grand dorsal, le trapèze, les rhomboïdes et le dentelé postérieur sont les principaux muscles superficiels du dos. Ils sont responsables de la stabilité et du mouvement de l\'omoplate et de la colonne vertébrale.\n' +
            '2. Muscles profonds : Les muscles érecteurs du rachis (spinaux) sont des muscles profonds qui s\'étendent le long de la colonne vertébrale. Ils sont impliqués dans le maintien de la posture, la flexion et l\'extension de la colonne vertébrale.\n' +
            '\n',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Vertèbres et colonne vertébrale',
          text: 'La colonne vertébrale est constituée de 33 vertèbres, divisées en cinq régions : cervicale, thoracique, lombaire, sacrée et coccygienne. Les vertèbres protègent la moelle épinière et jouent un rôle dans le soutien et la mobilité du dos.',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Innervation du dos',
          text: 'Le dos est innervé par les nerfs rachidiens, qui sortent de la colonne vertébrale à travers les espaces entre les vertèbres. Ces nerfs fournissent la sensibilité cutanée et contrôlent les muscles du dos.',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Utilité dans le sport',
          text: 'Le dos est essentiel dans de nombreux sports, en particulier ceux qui nécessitent une stabilité, une force et une mobilité du tronc. Par exemple, dans les sports de force, comme l\'haltérophilie, la musculation et le rugby, un dos fort est crucial pour la performance et la prévention des blessures.',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Risques de blessures possibles',
          text: 'Les blessures du dos peuvent inclure des entorses musculaires, des hernies discales, des fractures vertébrales et des tensions ligamentaires. Ces blessures peuvent être causées par des traumatismes, des mouvements incorrects, une utilisation excessive ou des problèmes posturaux. Les sports à impact, les sports de contact et les sports nécessitant des mouvements brusques du tronc augmentent le risque de blessure du dos.',
          // img: require('')
        },
        {
          color: 'cyan',
          title: 'Aspect clinique',
          text: 'En cas de blessure du dos, une évaluation clinique approfondie est nécessaire. Cela peut inclure des tests de mobilité, des examens neurologiques et des études d\'imagerie, telles que des radiographies, des IRM ou des scanners, pour évaluer l\'étendue des lésions. Le traitement peut varier en fonction de la nature de la blessure et peut inclure des approches conservatrices (repos, physiothérapie, médicaments) ou, dans les cas graves, une intervention chirurgicale. Une rééducation appropriée, la correction de la posture et des exercices de renforcement sont souvent nécessaires pour favoriser la guérison et prévenir les récidives. Un suivi médical et une gestion adéquate des blessures du dos sont importants pour assurer une récupération optimale.',
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
