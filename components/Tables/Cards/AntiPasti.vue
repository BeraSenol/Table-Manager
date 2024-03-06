<template>
  <UDivider
    :ui="{ label: 'text-primary-500 dark:text-primary-400 text-base' }"
    type="dashed"
    label="Anti Pasti"
  />
  <p class="my-4 mb-2 font-thin italic">
    {{ antiPastiCount }}
    <template v-if="antiPastiCount === 1"> Appetizer </template>
    <template v-else> Appetizers </template>
  </p>
  <UButton class="m-0.5 mb-6" size="2xs" color="red" variant="outline">
    Wait
  </UButton>
  <UButton class="m-0.5 mb-6" size="2xs" color="orange" variant="outline">
    Busy
  </UButton>
  <UButton class="m-0.5 mb-6" size="2xs" color="primary" variant="outline">
    Done
  </UButton>
</template>

<script lang="ts" setup>
const props = defineProps({
  antiPastiCount: {
    type: Number,
    required: true,
  },
});

const { antiPastiCount } = props;
</script>
