<template>
  <UDivider
    :ui="{ label: 'text-primary-500 dark:text-primary-400 text-base' }"
    type="dashed"
    label="Primi Piatti"
  />
  <p class="my-4 font-thin italic">
    {{ primiPiattiCount }}
    <template v-if="primiPiattiCount === 1"> First Course </template>
    <template v-else> First Course's </template>
  </p>
</template>

<script lang="ts" setup>
const props = defineProps({
  primiPiattiCount: {
    type: Number,
    required: true,
  },
});

const { primiPiattiCount } = props;
</script>
