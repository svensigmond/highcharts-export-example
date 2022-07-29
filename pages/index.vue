<template>
  <div ref="container"></div>
</template>

<script>
import Highcharts from "highcharts/highcharts.src";
import exporting from "highcharts/modules/exporting";

export default {
  name: "HomePage",

  mounted() {
	exporting(Highcharts);

    Highcharts.chart(this.$refs.container, {
      chart: {
        type: "column",
        styledMode: true,
      },

      title: {
        text: "Styling axes and columns",
      },

      yAxis: [
        {
          className: "highcharts-color-0",
          title: {
            text: "Primary axis",
          },
        },
        {
          className: "highcharts-color-1",
          opposite: true,
          title: {
            text: "Secondary axis",
          },
        },
      ],

      plotOptions: {
        column: {
          borderRadius: 5,
        },
      },

      series: [
        {
          data: [1, 3, 2, 4],
        },
        {
          data: [324, 124, 547, 221],
          yAxis: 1,
        },
      ],
    });
  },
};
</script>
