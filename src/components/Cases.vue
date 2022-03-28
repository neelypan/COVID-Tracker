<template>
  <div>
    <h2>Cases Today</h2>
    <p>{{ JSON.stringify(fetchData()) }}</p>
  </div>
</template>

<script lang="ts" setup>
defineProps({
  api: {
    type: String,
    required: true,
  },
});
</script>

<script lang="ts">
import { defineProps, onActivated } from 'vue';

const fetchData = async () => {
  const res = await fetch(api);
  const cases = await res.json();
  return cases;
};
onActivated(fetchData);
</script>
