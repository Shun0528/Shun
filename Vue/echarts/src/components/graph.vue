<script setup lang="ts">
import { use } from "echarts/core";
import { CanvasRenderer } from "echarts/renderers";
import { LineChart } from "echarts/charts";
import {
    TitleComponent,
    TooltipComponent,
    LegendComponent,
    GridComponent,
    DataZoomComponent,
} from "echarts/components";
import VChart from "vue-echarts";
import { ref } from "vue";

use([
    DataZoomComponent,
    GridComponent,
    CanvasRenderer,
    LineChart,
    TitleComponent,
    TooltipComponent,
    LegendComponent,
]);

const costGraphData = [
    { date: "01-01", cost: 1100 },
    { date: "01-02", cost: 1200 },
    { date: "01-03", cost: 1000 },
    { date: "01-04", cost: 800 },
    { date: "01-05", cost: 1700 },
    { date: "01-06", cost: 1000 },
    { date: "01-07", cost: 1000 },
    { date: "01-08", cost: 600 },
    { date: "01-09", cost: 800 },
    { date: "01-10", cost: 400 },
    { date: "01-11", cost: 1600 },
    { date: "01-12", cost: 1400 },
    { date: "01-13", cost: 1100 },
    { date: "01-14", cost: 1200 },
    { date: "01-15", cost: 900 },
];

const option = ref({
    title: {
        text: "Graph",
        left: "center",
    },
    tooltip: {
        trigger: "axis",
    },
    xAxis: {
        data: costGraphData.map((value: { date: any }) => {
            return value.date;
        }),
    },
    yAxis: {},
    dataZoom: [
        {
            startValue: 1,
        },
        {
            type: "inside",
        },
    ],
    series: {
        name: "cost",
        type: "line",
        data: costGraphData.map((value: { cost: any }) => {
            return value.cost;
        }),
    },
});
</script>

<template>
    <div>
        <v-chart class="chart" :option="option" />
    </div>
</template>

<style scoped>
.chart {
    height: 100vh;
}
</style>