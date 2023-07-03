<template>
  <div>
    <v-col cols="12" sm="6">
      <v-btn style="border-radius: 20px" @click="date_picker_dialog = true"
        >Changer de date
      </v-btn>
    </v-col>
    <v-col cols="12" sm="6">
      <v-alert v-if="no_data_warning" dense type="warning">
        Désoler nous avons pas trouver de données
      </v-alert>
    </v-col>
    <v-col cols="12" sm="6">
      <v-dialog v-model="date_picker_dialog" align="center" max-width="400px">
        <v-card align="center">
          <v-date-picker
            v-model="date_picker"
            next-icon="mdi-skip-next"
            prev-icon="mdi-skip-previous"
            range
            year-icon="mdi-calendar-blank"
          ></v-date-picker>
          <v-card-actions>
            <v-btn @click="OnValidateDatePicker">Valider</v-btn>
          </v-card-actions>
        </v-card>
      </v-dialog>
    </v-col>
    <v-row align="center">
      <client-only>
        <v-col cols="12">
          <e-charts
            ref="bar"
            :options="option"
            autoresize
            style="width: 100%"
          />
        </v-col>
      </client-only>
    </v-row>
  </div>
</template>

<script>
import ECharts from 'vue-echarts'
import 'echarts/theme/dark'
import moment from 'moment/moment'

export default {
  name: 'GraphStatsWeight',
  components: {
    ECharts,
  },
  data() {
    return {
      no_data_warning: false,
      graph_Key: 0,
      date_picker_dialog: false,
      date_picker: [],
      poids_user: [],
      option: {
        backgroundColor: 'rgb(43,89,86)',
        title: {
          textStyle: {
            color: 'white',
          },
          text: 'Graphique Evolution De Vôtre Poids',
          top: 10,
          left: 'center',
        },
        toolbox: {
          feature: {
            restore: {
              title: 'Restaurée zoom',
            },
            saveAsImage: {
              title: 'Sauvegarder en PNG',
            },
          },
        },
        xAxis: {
          axisLine: {
            show: true,
            lineStyle: {
              color: 'rgba(255, 255, 255, 1)',
            },
          },
          type: 'category',
          data: [],
        },
        yAxis: {
          type: 'value',
          axisLine: {
            show: true,
            lineStyle: {
              color: 'rgba(255, 255, 255, 1)',
            },
          },
        },
        dataZoom: [
          {
            type: 'inside',
            start: 0,
            end: 100,
          },
        ],
        tooltip: {
          trigger: 'item',
          axisPointer: {
            type: 'shadow',
            axis: 'x',
          },
        },
        series: [
          {
            color: 'blue',
            data: [],
            type: 'line',
          },
        ],
      },
    }
  },
  async fetch() {
    const actualDate = moment(new Date()).format('X')
    const treeMounthAgoDate = moment(new Date())
      .subtract(6, 'months')
      .format('X')
    try {
      await this.$axios
        .get('weight/' + treeMounthAgoDate + '/' + actualDate)
        .then((response) => {
          this.poids_user = response.data
          for (const item in this.poids_user) {
            this.poids_user[item].date = moment
              .unix(this.poids_user[item].date)
              .format('DD/MM/YYYY')
          }
          const values = this.poids_user.map((item) => item.value)
          const dates = this.poids_user.map((item) => item.date)
          this.option.series[0].data = values
          this.option.xAxis.data = dates
          this.graph_Key++
        })
    } catch (e) {
      console.log(e)
    }
  },
  methods: {
    async OnValidateDatePicker() {
      const firstdate = moment(this.date_picker[0]).format('X')
      const seconddate = moment(this.date_picker[1]).format('X')
      await this.$axios
        .get('weight/' + firstdate + '/' + seconddate)
        .then((response) => {
          if (response.data === null) {
            this.option.series[0].data = []
            this.option.xAxis.data = []
            this.no_data_warning = true
          } else {
            this.poids_user = response.data
            for (const item in this.poids_user) {
              this.poids_user[item].date = moment
                .unix(this.poids_user[item].date)
                .format('DD/MM/YYYY')
            }
            const values = this.poids_user.map((item) => item.value)
            const dates = this.poids_user.map((item) => item.date)
            this.option.series[0].data = values
            this.option.xAxis.data = dates
            this.no_data_warning = false
          }
        })
      this.graph_Key++
      this.date_picker_dialog = false
    },
  },
}
</script>

<style scoped></style>
