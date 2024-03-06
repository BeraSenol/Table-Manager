<template>
  <UDivider
    :ui="{ label: 'text-primary-500 dark:text-primary-400 text-base' }"
    type="dashed"
    label="Dolce"
  />
  <p class="mt-4 font-thin italic">
    {{ dolceCount }}
    <template v-if="dolceCount === 1"> Dessert </template>
    <template v-else> Desserts </template>
  </p>
</template>

<script lang="ts" setup>
const props = defineProps({
  dolceCount: {
    type: Number,
    required: true,
  },
});

const { dolceCount } = props;
</script>
