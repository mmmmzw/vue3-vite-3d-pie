<template>
  <div class="mycharts" ref="myChartsDom"></div>
</template>

<script setup>
import * as Echarts from "echarts";
import "echarts-gl";
import { reactive, onBeforeUnmount, onMounted, ref, watch } from "vue";
import { getParametricEquation, getHeight3D, getPie3D } from "./echart-option/right-center.js";
const myChartsDom = ref(null);
const data = reactive({
  dataList: [
    { name: "火警", value: 10, itemStyle: { color: "#ef8137", opacity: 0.6 } },
    { name: "设备故障1", value: 30, itemStyle: { color: "#f6c65a", opacity: 0.6 } },
    { name: "设备报警2", value: 40, itemStyle: { color: "#89ccf1", opacity: 0.6 } },
    { name: "设备报警3", value: 80, itemStyle: { color: "#25989e", opacity: 0.6 } },
  ],
});
let chart = null;
watch(
  () => data.dataList,
  (newVal, oldVal) => {
    if (data.dataList.length != 0) initChart();
  },
  { deep: true }
);

onMounted(() => {
  chart = Echarts.init(myChartsDom.value);
  initChart();
});

var optionConfig = {};

function initChart() {
  let option = getPie3D(data, data.dataList, 0.3);
  chart.setOption(option);
}
</script>

<style lang="scss" scoped>
.mycharts {
  width: 100%;
  height: 100vh;
}
</style>
