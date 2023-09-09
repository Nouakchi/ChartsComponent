<script setup>
import ChartComponent from './components/ChartComponent.vue';

const labels = ['WASHINGTON', 'OREGON', 'CALIFORNIA', 'NEVADA', 'IDAHO', 'MONTANA', 'WYOMING'];

const data = {
      labels: labels,
      datasets: [
        {
            label: 'Votes for Donald trump',
            data: [1584651, 958448, 6006429, 669890, 554119, 343602, 193559],
            borderWidth: 1,
            backgroundColor: [
              'rgba(255, 99, 132)',
              'rgba(255, 159, 64)',
              'rgba(255, 205, 86)',
              'rgba(75, 192, 192)',
              'rgba(54, 162, 235)',
              'rgba(153, 102, 255)',
              'rgba(201, 203, 207)'
            ],
        }
        ]
    };

const options = {
  plugins: {
            legend: {
                labels: {
                    font: {
                        size: 12,
                    }
                }
            }
        }
      };

    const charts1 = {
      element: [
        {
          title: 'bar',
          subtitle: 'bar subtitle',
          id:'barChart',
          type: 'bar',
          chart: {
            data: data,
            options: options
          }
        },
        {
          title: 'pie',
          subtitle: 'pie subtitle',
          id:'pieChart',
          type: 'line',
          chart: {
            data: data,
            options: options
          }
        },
      ]
    }

    const charts2 = {
      element: [
        {
          title: 'doughnut',
          subtitle: 'doughnut subtitle',
          id:'doughnutChart',
          type: 'doughnut',
          chart: {
            data: data,
            options: options
          }
        },
        {
          title: 'polarArea',
          subtitle: 'polarArea subtitle',
          id:'polarAreaChart',
          type: 'polarArea',
          chart: {
            data: data,
            options: options
          }
        },
        {
          title: 'radar',
          subtitle: 'radar subtitle',
          id:'radarChart',
          type: 'radar',
          chart: {
            data: data,
            options: options
          }
        },
      ]
    }

</script>

<template>
  <body>
   <div class="container">
    <div class="child">
      <ChartComponent
        v-for="item in charts1.element"
        v-bind="item" 
        :type="item.type" 
        :title="item.title"
        :subtitle="item.subtitle"
        :id="item.id"
      />
    </div>
    <div class="child">
      <ChartComponent
        v-for="item in charts2.element"
        v-bind="item" 
        :type="item.type" 
        :title="item.title"
        :subtitle="item.subtitle"
        :id="item.id"
      />
    </div>
  </div>
  </body>
</template>

<style scoped>

body{
  background-color: rgb(165, 165, 165);
  padding: 10px;
}

.child {
  margin: 10px;
  display: flex;
  justify-content: space-evenly;
  align-items: center;
}

.element {
  margin: 10px;
  width: 100%;
}

.test
{
  padding: 20px;
  background-color: rgb(230, 228, 228);
}

</style>
