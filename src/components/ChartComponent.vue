<template>
          <v-card :title="title"
                  :subtitle="subtitle"
                  elevation="12"
                  class="test rounded-shaped"
                  >
                  <canvas :id="id"></canvas>
          </v-card>
</template>

<script setup>

import Chart from 'chart.js/auto';
import { onMounted } from 'vue';

const props = defineProps({
    title: String,
    subtitle: String,
    id: String,
    type: String,
    chart: Object
})

onMounted( () =>{
    // eslint-disable-next-line no-new
    new Chart(
        document.getElementById(props.id),
        {
          type: props.type,
          data: props.chart.data,
          options: props.chart.options
        }
    )
  });

</script>

<style scoped>

.test
{
  padding: 20px;
  background-color: rgb(230, 228, 228);
  margin: 10px;
  width: 100%;
}

</style>