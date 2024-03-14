<template>
  <UDivider
    :ui="{
      label: 'text-primary-500 dark:text-primary-500 text-base',
      border: {
        base: 'border-primary-200 dark:border-primary-800',
      },
    }"
    type="solid"
    label="Primi Piatti"
    size="xs"
    v-if="tableState[tableNumber - 1][1] === 'Done'"
  />
  <UDivider
    :ui="{
      label: 'text-yellow-500 dark:text-yellow-500 text-base',
      border: {
        base: 'border-yellow-200 dark:border-yellow-800',
      },
    }"
    type="solid"
    label="Primi Piatti"
    size="xs"
    v-if="tableState[tableNumber - 1][1] === 'Busy'"
  />
  <UDivider
    :ui="{
      label: 'text-red-500 dark:text-red-500 text-base',
      border: {
        base: 'border-red-200 dark:border-red-800',
      },
    }"
    type="solid"
    label="Primi Piatti"
    size="xs"
    v-if="tableState[tableNumber - 1][1] === 'Wait'"
  />
  <p class="my-2 font-thin italic">
    {{ primiPiattiCount }}
    <template v-if="primiPiattiCount === 1"> First Course </template>
    <template v-else> First Course's </template>
  </p>
  <UButtonGroup>
    <UButton
      @click="tableState[tableNumber - 1][1] = 'Wait'"
      class="m-0.5 mb-6"
      size="2xs"
      color="red"
      variant="soft"
    >
      Wait
    </UButton>
    <UButton
      @click="tableState[tableNumber - 1][1] = 'Busy'"
      class="m-0.5 mb-6"
      size="2xs"
      color="yellow"
      variant="soft"
    >
      Busy
    </UButton>
    <UButton
      @click="tableState[tableNumber - 1][1] = 'Done'"
      class="m-0.5 mb-6"
      size="2xs"
      color="primary"
      variant="soft"
    >
      Done
    </UButton>
  </UButtonGroup>
</template>

<script lang="ts" setup>
import { useTableState } from "~/composables/states";

const props = defineProps({
  primiPiattiCount: {
    type: Number,
    required: true,
  },
  tableNumber: {
    type: Number,
    required: true,
  },
});

const { primiPiattiCount } = props;
const tableState = useTableState();
</script>
