<template>
  <UDivider
    :ui="{
      label: 'text-primary-500 dark:text-primary-400 text-base',
      border: {
        base: 'border-primary-200 dark:border-primary-800',
      },
    }"
    type="dashed"
    label="Anti Pasti"
    size="xs"
  />
  <p class="my-2 mb-2 font-thin italic">
    {{ antiPastiCount }}
    <template v-if="antiPastiCount === 1"> Appetizer </template>
    <template v-else> Appetizers </template>
  </p>
  <UButton
    @click="tableState[tableNumber - 1] = 'Wait'"
    class="m-0.5 mb-6"
    size="2xs"
    color="red"
    variant="outline"
  >
    Wait
  </UButton>
  <UButton
    @click="tableState[tableNumber - 1] = 'Busy'"
    class="m-0.5 mb-6"
    size="2xs"
    color="orange"
    variant="outline"
  >
    Busy
  </UButton>
  <UButton
    @click="tableState[tableNumber - 1] = 'Done'"
    class="m-0.5 mb-6"
    size="2xs"
    color="primary"
    variant="outline"
  >
    Done
  </UButton>
</template>

<script lang="ts" setup>
import { useTableState } from "~/composables/states";

const props = defineProps({
  antiPastiCount: {
    type: Number,
    required: true,
  },
  tableNumber: {
    type: Number,
    required: true,
  },
});

const { antiPastiCount } = props;
const tableState = useTableState();
</script>
