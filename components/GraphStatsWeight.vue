<template>
  <div>
    <v-row>
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
      .subtract(3, 'months')
      .format('X')
    try {
      await this.$axios
        .get('weight/' + treeMounthAgoDate + '/' + actualDate)
        .then((response) => {
          this.poids_user = response.data
          for (const item in this.poids_user) {
            this.poids_user[item].date = moment
              .unix(this.poids_user[item].date)
              .format('DD/MM')
          }
          const values = this.poids_user.map((item) => item.value)
          const dates = this.poids_user.map((item) => item.date)
          this.option.series[0].data = values
          this.option.xAxis.data = dates
        })
    } catch (e) {
      console.log(e)
    }
  },
}
</script>

<style scoped></style>
