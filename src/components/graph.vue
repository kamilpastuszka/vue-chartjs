<template>
  <div id="app">
    <div id="main"><canvas ref="chartjs"></canvas></div>
  </div>
</template>

<script>
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
    let coutries = Object.keys(this.population2017),
      data2017 = Object.values(this.population2017),
      data2050 = Object.values(this.population2050);

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
              backgroundColor: [
                "rgba(255, 99, 132, 0.2)",
                "rgba(54, 162, 235, 0.2)",
                "rgba(255, 206, 86, 0.2)",
                "rgba(75, 192, 192, 0.2)",
                "rgba(153, 102, 255, 0.2)",
                "rgba(255, 99, 132, 0.2)",
                "rgba(54, 162, 235, 0.2)",
                "rgba(255, 206, 86, 0.2)",
                "rgba(75, 192, 192, 0.2)",
                "rgba(153, 102, 255, 0.2)",
                "rgba(255, 159, 64, 0.2)"
              ],
              borderColor: [
                "rgba(255,99,132,1)",
                "rgba(54, 162, 235, 1)",
                "rgba(255, 206, 86, 1)",
                "rgba(75, 192, 192, 1)",
                "rgba(153, 102, 255, 1)",
                "rgba(255,99,132,1)",
                "rgba(54, 162, 235, 1)",
                "rgba(255, 206, 86, 1)",
                "rgba(75, 192, 192, 1)",
                "rgba(153, 102, 255, 1)",
                "rgba(255, 159, 64, 1)"
              ],
              borderWidth: 2
            },
            {
              label: "Projection for 2050",
              data: data2050,
              backgroundColor: [
                "rgba(255, 99, 132, 0.2)",
                "rgba(54, 162, 235, 0.2)",
                "rgba(255, 206, 86, 0.2)",
                "rgba(75, 192, 192, 0.2)",
                "rgba(153, 102, 255, 0.2)",
                "rgba(255, 99, 132, 0.2)",
                "rgba(54, 162, 235, 0.2)",
                "rgba(255, 206, 86, 0.2)",
                "rgba(75, 192, 192, 0.2)",
                "rgba(153, 102, 255, 0.2)",
                "rgba(255, 159, 64, 0.2)"
              ],
              borderColor: [
                "rgba(255,99,132,1)",
                "rgba(54, 162, 235, 1)",
                "rgba(255, 206, 86, 1)",
                "rgba(75, 192, 192, 1)",
                "rgba(153, 102, 255, 1)",
                "rgba(255,99,132,1)",
                "rgba(54, 162, 235, 1)",
                "rgba(255, 206, 86, 1)",
                "rgba(75, 192, 192, 1)",
                "rgba(153, 102, 255, 1)",
                "rgba(255, 159, 64, 1)"
              ],
              borderWidth: 1
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
#main {
  max-width: 900px;
}
</style>
