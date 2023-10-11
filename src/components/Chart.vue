<template>
  <div class="chart-wrapper">
    <h2>{{ header }}</h2>

    <DxChart id="chart" :data-source="chartData" palette="Violet" width="100%">
      <DxCommonSeriesSettings
        argument-field="report_dt"
        value-field="cnt"
        type="spline"
      >
        <DxPoint :visible="false" />
      </DxCommonSeriesSettings>
      <DxValueAxis>
        <DxGrid :visible="false" />
      </DxValueAxis>
      <DxArgumentAxis>
        <DxLabel :visible="false" />
      </DxArgumentAxis>
      <DxSeries color="#4176fa" />
      <DxLegend :visible="false" />
      <DxTooltip :enabled="true" />
    </DxChart>
  </div>
</template>
<script setup>
import { computed } from "vue";
import DataSource from "devextreme/data/data_source";
import {
  DxChart,
  DxSeries,
  DxCommonSeriesSettings,
  DxArgumentAxis,
  DxLabel,
  DxPoint,
  DxGrid,
  DxLegend,
  DxTooltip,
  DxValueAxis,
} from "devextreme-vue/chart";

const header = "Download per month";
const chartData = new DataSource({
  key: 'report_dt',
  load() {
    return fetch('https://710ede90.artydev.ru/api/v1/daily_stats/').then(res => res.json()).then(data => data.data)
  }
})
</script>

<style lang="scss" scoped>
.chart-wrapper {
  width: 40%;
  text-align: center;
}
.read-the-docs {
  color: #888;
}
</style>
