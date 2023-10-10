<template>
  <div class="chart-wrapper">
    <h2>{{ header }}</h2>

    <DxChart id="chart" :data-source="chartData" palette="Violet" width="100%">
      <DxCommonSeriesSettings
        argument-field="date"
        value-field="count"
        type="spline"
      >
        <DxPoint :visible="false" />
      </DxCommonSeriesSettings>
      <DxValueAxis>
        <DxGrid :visible="false" />
      </DxValueAxis>
      <DxArgumentAxis>
        <DxLabel :visible="false" :customize-text="customizeText" />
      </DxArgumentAxis>
      <DxSeries color="#4176fa" />
      <DxLegend :visible="false" />
      <DxTooltip :enabled="true" />
    </DxChart>
  </div>
</template>
<script setup>
import { ref } from "vue";
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
let chartData = ref([
  {
    date: "2023-10-02T21:50:00Z",
    count: 187,
  },
  {
    date: "2023-10-03T21:50:00Z",
    count: 333,
  },
  {
    date: "2023-10-04T21:50:00Z",
    count: 697,
  },
  {
    date: "2023-10-05T21:50:00Z",
    count: 324,
  },
  {
    date: "2023-10-06T21:50:00Z",
    count: 1389,
  },
  {
    date: "2023-10-07T21:50:00Z",
    count: 611,
  },
  {
    date: "2023-10-08T21:50:00Z",
    count: 187,
  },
]);
const customizeText = ({ valueText }) => {
  let date = new Date(valueText);
  return new Intl.DateTimeFormat("ru-RU").format(date);
};
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
