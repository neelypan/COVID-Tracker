<script setup lang="ts">
import Cases from './Cases/index.vue';
import Deaths from './Deaths/index.vue';
</script>

<template>
  <div>
    <Cases />
    <Deaths />
  </div>
</template>

<style>
.div {
  display: inline-block;
  margin: 6px;
  border-radius: 6px;
  background: rgb(235, 221, 221);
  width: max-content;
  height: max-content;
}
</style>
