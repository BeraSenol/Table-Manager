<template>
  <p class="font-thin italic">
    {{ plateCount }}
    <template v-if="plateCount === 1"> Plate </template>
    <template v-else> Plates </template>
  </p>
</template>

<script lang="ts" setup>
const props = defineProps({
  plateCount: {
    type: Number,
    required: true,
  },
});

const { plateCount } = props;
</script>
