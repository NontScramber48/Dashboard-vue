<template>
  <div>
    <!--Stats cards-->
    <div class="row">
      <div
        class="col-md-6 col-xl-4"
        v-for="stats in statsCards"
        :key="stats.title"
      >
        <stats-card>
          <div
            class="icon-big text-center"
            :class="`icon-${stats.type}`"
            slot="header"
          >
            <i :class="stats.icon"></i>
          </div>
          <div class="numbers" slot="content">
            <p>{{ stats.title }}</p>
            {{ stats.value }}
          </div>
          <div class="stats" slot="footer">
            <sidebar-link to="/table-list" name="">
              More Information</sidebar-link
            >
          </div>
        </stats-card>
      </div>
    </div>

    <!--Charts-->
    <div class="row">
      <div class="col-12">
        <chart-card
          title="เปรียบเทียบยอดขายรายสัปดาห์"
          sub-title=""
          :chart-data="usersChart.data"
          :chart-options="usersChart.options"
        >
          <span slot="footer">
            <i class="ti-reload"></i> Updated 3 minutes ago
          </span>
          <div slot="legend">
            <i class="fa fa-circle text-info"></i> Delivery
            <!-- <i class="fa fa-circle text-danger"></i> Click -->
            <i class="fa fa-circle text-warning"></i> Walk in
          </div>
        </chart-card>
      </div>

      <div class="col-md-6 col-12">
        <chart-card
          title="เปรียบเทียบรายได้/ค่าใช้จ่าย"
          sub-title="  "
          :chart-data="preferencesChart.data"
          chart-type="Pie"
        >
          <span slot="footer">
            <i class="ti-timer"></i> Campaign set 2 days ago</span
          >
          <div slot="legend">
            <i class="fa fa-circle text-info"></i> รายได้
            <!-- <i class="fa fa-circle text-danger"></i> Bounce -->
            <i class="fa fa-circle text-warning"></i> ค่าใช้จ่าย
          </div>
        </chart-card>
      </div>

      <div class="col-md-6 col-12">
        <chart-card
          title="เปรียบเทียบยอดขายรายเดือน "
          sub-title="   "
          :chart-data="activityChart.data"
          :chart-options="activityChart.options"
        >
          <span slot="footer">
            <i class="ti-check"></i> Data information certified
          </span>
          <div slot="legend">
            <i class="fa fa-circle text-info"></i> Delivery
            <i class="fa fa-circle text-warning"></i> Walk in
          </div>
        </chart-card>
      </div>
    </div>
  </div>
</template>
<script setup>
import { StatsCard, ChartCard } from "@/components/index";
import { ref } from "vue";
// import { router } from "vue";
import Chartist from "chartist";

const statsCards = ref([
  {
    type: "warning",
    icon: "ti-bar-chart",
    title: "ยอดขายรายวัน",
    value: "฿1,345",
    footerText: "Updated now",
    footerIcon: "ti-reload",
  },
  {
    type: "success",
    icon: "ti-bar-chart",
    title: "ยอดขายรายสัปดาห์",
    value: "฿31,345",
    footerText: "Last day",
    footerIcon: "ti-calendar",
  },
  {
    type: "danger",
    icon: "ti-bar-chart",
    title: "ยอดขายรายเดือน",
    value: "฿131,345",
    footerText: "In the last hour",
    footerIcon: "ti-timer",
  },
]);
const usersChart = ref({
  data: {
    labels: [
      "Sunday",
      "Monday",
      "tuesday",
      "wendesday",
      "thursday",
      "Friday",
      "Sat",
      "",
    ],
    series: [
      [287, 385, 490, 100, 150, 626, 698, 895, 952],
      [67, 152, 193, 240, 387, 435, 535, 642, 744],
      // [23, 113, 67, 108, 190, 239, 307, 410, 410],
    ],
  },
  options: {
    low: 0,
    high: 1000,
    showArea: true,
    height: "245px",
    axisX: {
      showGrid: false,
    },
    lineSmooth: Chartist.Interpolation.simple({
      divisor: 3,
    }),
    showLine: true,
    showPoint: false,
  },
});
const activityChart = ref({
  data: {
    labels: [
      "Jan",
      "Feb",
      "Mar",
      "Apr",
      "Mai",
      "Jun",
      "Jul",
      "Aug",
      "Sep",
      "Oct",
      "Nov",
      "Dec",
    ],
    series: [
      [542, 543, 520, 680, 653, 753, 326, 434, 568, 610, 756, 895],
      [230, 293, 380, 480, 503, 553, 600, 664, 698, 710, 736, 795],
    ],
  },
  options: {
    seriesBarDistance: 10,
    axisX: {
      showGrid: false,
    },
    height: "245px",
  },
});
const preferencesChart = ref({
  data: {
    labels: ["72%", "28%"],
    series: [72, 28],
  },
  options: {},
});
// function Goto() {
//   router.push({ path: "/table-list" });
// }
</script>
<style></style>
