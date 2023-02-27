<template>
  <v-row>
    <client-only>
      <v-col cols="12">
        <e-charts
          ref="bar"
          :options="option"
          :theme="graphDarkTheme"
          autoresize
          style="width: 100%"
        />
      </v-col>
    </client-only>
  </v-row>
</template>

<script>
import ECharts from 'vue-echarts'
import 'echarts/lib/chart/line'
import 'echarts/lib/component/tooltip'
import 'echarts/lib/component/title'
import 'echarts/theme/dark'
export default {
  name: 'GraphStatsWaeight',
  components: {
    ECharts
  },
  data () {
    return {
      option: {
        title: {
          text: 'Graphique Evolution De Vôtre Poids',
          top: 10,
          left: 'center'

        },
        xAxis: {
          type: 'category',
          data: ['01/12', '02/01', '02/24', '03/10', '04/01', '04/31', '05/28']
        },
        yAxis: {
          type: 'value'
        },
        tooltip: {

          trigger: 'item',
          axisPointer: {
            type: 'shadow',
            axis: 'x'
          }
        },
        series: [
          {
            data: [60, 62, 63, 65, 66.5, 68, 90],
            type: 'line'
          }
        ]
      }
    }
  },
  computed: {
    graphDarkTheme () {
      return this.$vuetify.theme.dark ? 'dark' : ''
    }
  }

}
</script>

<style scoped>

</style>
