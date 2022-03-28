<template>
  <div class="div">
    <h2>Cases Today</h2>
    <p>{{ JSON.stringify(fetchData()) }}</p>
  </div>
</template>

<script lang="ts" setup>
import { onMounted } from 'vue';

const fetchData = async () => {
  const res = await fetch('https://disease.sh/v3/covid-19/all');
  const json = await res.json();

  return json.todayCases;
};

onMounted(fetchData);

console.log(fetchData);
</script>

<style>
.div {
  display: inline-block;
  margin: 6px;
  border-radius: 6px;
}
</style>
