<template>
<div>
  <v-row>
    <client-only>
    <v-col cols="12">
      <e-charts
      ref="bar"
      :options="option"
      autoresize
      style="width: 100% "
      />
    </v-col>
    </client-only>
  </v-row>
</div>
</template>

<script>
import ECharts from 'vue-echarts'
import 'echarts/theme/dark'

export default {
  name: "GraphStatsWeight",
  components:{
    ECharts
  },
  data () {
    return {
      option: {
        backgroundColor: 'rgb(43,89,86)',
        title: {
          textStyle:{
            color: 'white',
          },
          text: 'Graphique Evolution De Vôtre Poids',
          top: 10,
          left: 'center'

        },
        toolbox: {
          feature: {
            restore: {
              title: 'Restaurée zoom'
            },
            saveAsImage: {
              title: 'Sauvegarder en PNG'
            }
          }
        },
        xAxis: {
          axisLine: {
            show: true,
            lineStyle: {
              color: "rgba(255, 255, 255, 1)"
            }
          },
          type: 'category',
          data: ['01/12', '02/01', '02/24', '03/10', '04/01', '04/31', '05/28']
        },
        yAxis: {
          type: 'value',
          axisLine: {
            show: true,
            lineStyle: {
              color: "rgba(255, 255, 255, 1)"
            }
          },
        },
        dataZoom: [
          {
            type: 'inside',
            start: 0,
            end: 100
          },
        ],
        tooltip: {

          trigger: 'item',
          axisPointer: {
            type: 'shadow',
            axis: 'x'
          }
        },
        series: [
          {
            color: 'blue',
            data: [60, 62, 63, 65, 66.5, 68, 90],
            type: 'line'
          }
        ]
      }
    }
  }
}
</script>

<style scoped>

</style>
