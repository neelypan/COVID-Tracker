<template>
  <div class="div">
    <h4>Cases Today</h4>
    <p>
      {{ data }}
    </p>
  </div>
</template>

<script lang="ts" setup>
import { onMounted, ref } from 'vue';

const data = ref(null);

const fetchData = async () => {
  const res = await fetch('https://disease.sh/v3/covid-19/all/');
  const json = await res.json();
  return json.todayCases;
};
const processData = async () => {
  await fetchData()
    .then(
      (val) =>
        // TODO: get the data to only update if the number is different
        (data.value = val.toLocaleString('en-US'))
    )
    .catch((err) => console.error(err));
};
setInterval(processData, 600000);
onMounted(processData);
</script>
