<script setup>
import TableCols from './TableCols.vue';

const props = defineProps({
  data: Array,
  indx: Number
});

const index = props.indx;
</script>

<template>
  <div class="m-0.5 flex">
    <TableCols v-for="(arrayValue, arrayKey) in props.data" 
    :value="arrayValue" :k="arrayKey" :indx="index" />
  </div>
</template>
