<script setup>
const props = defineProps({
  value: Number,
  k: Number,
  indx: Number,
});

</script>

<template class="m-0.5 flex">
  <div class="m-0.5 text-md bg-gray-400" v-if="props.value == 1 && props.k != 0">{{ value }}</div>
  <div class="m-0.5 text-md bg-gray-200" v-if="props.value == 0 && props.k != 0">{{ value }}</div>
  <div class="m-0.5 text-md" v-if="props.k == 0 && props.indx >= 10">{{ indx }}</div>
  <div class="m-0.5 text-md" v-if="props.k == 0 && props.indx < 10">&nbsp; {{ indx }}</div>
</template>
