<template>
  <UDivider
    :ui="{ label: 'text-primary-500 dark:text-primary-400 text-base' }"
    type="dashed"
    label="Secondi Piatti"
  />
  <p class="my-4 font-thin italic">
    {{ secondiPiattiCount }}
    <template v-if="secondiPiattiCount === 1"> Second Course</template>
    <template v-else> Second Courses </template>
  </p>
</template>

<script lang="ts" setup>
const props = defineProps({
  secondiPiattiCount: {
    type: Number,
    required: true,
  },
});

const { secondiPiattiCount } = props;
</script>
