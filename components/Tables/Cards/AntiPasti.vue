<template>
  <UDivider
    :ui="{
      label: 'text-primary-500 dark:text-primary-500 text-base',
      border: {
        base: 'border-primary-200 dark:border-primary-800',
      },
    }"
    type="solid"
    label="Anti Pasti"
    size="xs"
    v-if="tableState[tableNumber - 1][0] === 'Done'"
  />
  <UDivider
    :ui="{
      label: 'text-yellow-500 dark:text-yellow-500 text-base',
      border: {
        base: 'border-yellow-200 dark:border-yellow-800',
      },
    }"
    type="solid"
    label="Anti Pasti"
    size="xs"
    v-if="tableState[tableNumber - 1][0] === 'Busy'"
  />
  <UDivider
    :ui="{
      label: 'text-red-500 dark:text-red-500 text-base',
      border: {
        base: 'border-red-200 dark:border-red-800',
      },
    }"
    type="solid"
    label="Anti Pasti"
    size="xs"
    v-if="tableState[tableNumber - 1][0] === 'Wait'"
  />
  <p class="my-2 mb-2 font-thin italic">
    {{ antiPastiCount }}
    <template v-if="antiPastiCount === 1"> Appetizer </template>
    <template v-else> Appetizers </template>
  </p>
  <UButtonGroup>
    <UButton
      @click="tableState[tableNumber - 1][0] = 'Wait'"
      class="m-0.5 mb-6"
      size="2xs"
      color="red"
      variant="soft"
    >
      Wait
    </UButton>
    <UButton
      @click="tableState[tableNumber - 1][0] = 'Busy'"
      class="m-0.5 mb-6"
      size="2xs"
      color="yellow"
      variant="soft"
    >
      Busy
    </UButton>
    <UButton
      @click="tableState[tableNumber - 1][0] = 'Done'"
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
