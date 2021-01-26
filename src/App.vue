<template>
  <v-app>
    <Navbar />
    
    <v-main class="mt-4">
      <h1 class="ml-8"><v-icon class="mr-3 mb-1 fontIcon">fas fa-tachometer-alt</v-icon>Driver Dashboard</h1>
      <v-container>
        <v-row class="mt-4">
          <v-col md="6">
            <h1 class="hedline mb-2 gray--text"><v-icon class="mr-3 mb-2 fontIcon">fas fa-gas-pump</v-icon>Mileage Tracker</h1>
            <template>
              <div id="app">
                <MileageTracker />
              </div>
            </template>
          </v-col>
          <v-spacer></v-spacer>
          <v-col md="6">
            <h1 class="hedline mb-2 gray--text"><v-icon class="mr-3 mb-1 fontIcon">fas fa-calendar-alt</v-icon>Driver Calendar</h1>
            <template>
              <div id="app">
                <Calendar />
              </div>
            </template>
          </v-col>
        </v-row>
        <v-row class="mt-4 mb-12">
          <v-col md="6">
            <h1 class="hedline mb-2 gray--text"><v-icon class="mr-3 mb-2 fontIcon">fas fa-coins</v-icon>Driver Monthly Income</h1>
            <template>
              <div id="app">
                  <Profits/>
              </div>
            </template>
          </v-col>
          <v-col md="6">
            <h1 class="hedline mb-2 gray--text"><v-icon class="mr-3 mb-2 fontIcon">fas fa-money-check-alt</v-icon>Driver Yearly Performance</h1>
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
import Calendar from "./components/Calendar";
import MileageTracker from "./components/MileageTracker";
import Profits from "./components/Profits";


export default {
  name: "App",
  components: {
    GChart,
    Navbar,
    Calendar,
    MileageTracker,
    Profits
  },
  data() {
    return {
      chartsLib: null,
      // Array will be automatically processed with visualization.arrayToDataTable function
      chartData: [
        ["Year", "Miles", "Expenses", "Profit"],
        ["2018", 222000, 15600, 25600],
        ["2019", 130000, 20000, 25000],
        ["2020", 234000, 32000, 52000],
        ["2021", 22000, 24000, 54000],

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
        colors: ["#ff4081", "#000000", "#2BC9D7"],
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

<style scoped>
.fontIcon {
  color: black;
}
</style>
