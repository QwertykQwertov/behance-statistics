<template>
  <div class="chart-wrapper">
    <h2>{{ header }}</h2>

    <DxChart id="chart" :data-source="chartData" palette="Violet" width="100%" height="350">
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
      <DxTooltip :enabled="true" content-template="tooltipTemplate" />
      <template #tooltipTemplate="{ data }">
        <ToolTipTemplate :info="data" />
      </template>
    </DxChart>
  </div>
</template>
<script setup>
import ToolTipTemplate from "./TooltipTemplate.vue";
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
  key: "report_dt",
  load() {
    return fetch("https://710ede90.artydev.ru/api/v1/daily_stats/")
      .then((res) => res.json())
      .then((data) => data.data);
  },
});
const customizeTooltip = (arg) => {
  return {
    text: `Date: ${arg.argument} 
 
 Downloads: ${arg.value}`,
  };
};
</script>

<style lang="scss" scoped>
.chart-wrapper {
  min-width: 500px;
  width: 40%;
  text-align: center;
}
@media (max-width: 1000px) {
  .chart-wrapper{
    min-width: 0; 
    width: 95%;

  }
}

.read-the-docs {
  color: #888;
}
</style>
