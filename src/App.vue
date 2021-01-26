<template>
  <v-app>
    <Navbar />
    <v-main>
      <v-container>
        <v-row no-gutters>
          <v-col md="6">
            <h1 class="hedline mb-2 grey--text">The Inconme Growth</h1>
            <template>
              <div id="app">
                <GChart
                  :settings="{ packages: ['bar'] }"
                  :data="chartData"
                  :options="chartOptions"
                  :createChart="(el, google) => new google.charts.Bar(el)"
                  @ready="onChartReady"
                />
              </div>
            </template>
          </v-col>
          <v-col md="6">
            <h1 class="hedline mb-2 grey--text">The Inconme Growth</h1>
            <template>
              <div id="app">
                <GChart
                  :settings="{ packages: ['bar'] }"
                  :data="chartData"
                  :options="chartOptions"
                  :createChart="(el, google) => new google.charts.Bar(el)"
                  @ready="onChartReady"
                />
              </div>
            </template>
          </v-col>
        </v-row>
                <v-row no-gutters>
          <v-col md="6">
            <h1 class="hedline mb-2 grey--text">The Inconme Growth</h1>
            <template>
              <div id="app">
                <GChart
                  :settings="{ packages: ['bar'] }"
                  :data="chartData"
                  :options="chartOptions"
                  :createChart="(el, google) => new google.charts.Bar(el)"
                  @ready="onChartReady"
                />
              </div>
            </template>
          </v-col>
          <v-col md="6">
            <h1 class="hedline mb-2 grey--text">The Inconme Growth</h1>
            <template>
              <div id="app">
                <GChart
                  :settings="{ packages: ['bar'] }"
                  :data="chartData"
                  :options="chartOptions"
                  :createChart="(el, google) => new google.charts.Bar(el)"
                  @ready="onChartReady"
                />
              </div>
            </template>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
import { GChart } from "vue-google-charts";
import Navbar from "./components/Navbar";

export default {
  name: "App",
  components: {
    GChart,
    Navbar,
  },
  data() {
    return {
      chartsLib: null,
      // Array will be automatically processed with visualization.arrayToDataTable function
      chartData: [
        ["Year", "Sales", "Expenses", "Profit"],
        ["2014", 1000, 400, 200],
        ["2015", 1170, 460, 250],
        ["2016", 660, 1120, 300],
        ["2017", 1030, 540, 350],
      ],
    };
  },
  computed: {
    chartOptions() {
      if (!this.chartsLib) return null;
      return this.chartsLib.charts.Bar.convertOptions({
        chart: {
          title: "Company Performance",
          subtitle: "Sales, Expenses, and Profit: 2014-2017",
        },
        bars: "horizontal", // Required for Material Bar Charts.
        hAxis: { format: "decimal" },
        height: 400,
        colors: ["#1b9e77", "#d95f02", "#7570b3"],
      });
    },
  },
  methods: {
    onChartReady(chart, google) {
      this.chartsLib = google;
    },
  },
};
</script>

<style scoped></style>
