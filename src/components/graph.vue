<template>
  <div id="app">
    <h2>
      Population in 2017 and forecast for 2050 of EU biggest member states </br> (in
      millions)
    </h2>
    <br>
    <div id="main"><canvas ref="chartjs"></canvas></div>
      <p><strong>Source:</strong> Statista.com (data as of November 2017)</p>
  </div>

</template>

<script>
import _ from "lodash";

export default {
  name: "Graph",
  data() {
    return {
      population2017: {
        Germany: 83.1,
        "United Kingdom": 66.2,
        France: 65,
        Italy: 60.5,
        Spain: 46.6,
        Poland: 38.4,
        Romania: 19.6,
        Netherlands: 17.1,
        Balgium: 11.3,
        Greece: 10.7
      },
      population2050: {
        Germany: 83.2,
        "United Kingdom": 77.7,
        France: 72.3,
        Italy: 57.5,
        Spain: 44.4,
        Poland: 32.6,
        Romania: 13.9,
        Netherlands: 18.1,
        Balgium: 12.7,
        Greece: 9.1
      }
    };
  },

  mounted() {
    const coutries = Object.keys(this.population2017),
      data2017 = Object.values(this.population2017),
      data2050 = Object.values(this.population2050);

    const backgroundColor2017 = _.times(10, () => "#30336b"),
     backgroundColor2050 = _.times(10, () => "#4b7bec"),
     //backgroundColor2050 = _.times(10, () => "#95afc0"),
     borderColor2017 = _.times(10, () => "#130f40"),
      borderColor2050 = _.times(10, () => "#4b6584");

    const chart = this.$refs.chartjs,
      ctx = chart.getContext("2d"),
      populationChart = new Chart(ctx, {
        type: "bar",
        data: {
          labels: coutries,
          datasets: [
            {
              label: "Population in 2017",
              data: data2017,
              backgroundColor: backgroundColor2017,
              borderColor: borderColor2017,
              borderWidth: 0.5
            },
            {
              label: "Projection for 2050",
              data: data2050,
              backgroundColor: backgroundColor2050,
              borderColor: borderColor2050,
              borderWidth: 0.5
            }
          ]
        },
        options: {
          legend: {
            display: true
          },
          scales: {
            yAxes: [
              {
                ticks: {
                  beginAtZero: true
                }
              }
            ]
          }
        }
      });
  }
};
</script>

<style scoped>
#app {
  max-width: 900px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  margin: 0 auto;
  height: 100vh;
}
@media (max-width: 768px) 
{
  h2 {
  font-size: 1em;
  } 
  p {
    font-size: 0.8em;
  }
}
</style>
