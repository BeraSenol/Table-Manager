<template>
  <UDivider
    :ui="{
      label: 'text-primary-500 dark:text-primary-500 text-base',
      border: {
        base: 'border-primary-200 dark:border-primary-800',
      },
    }"
    type="solid"
    label="Secondi Piatti"
    size="xs"
    v-if="tableState[tableNumber - 1][2] === 'Done'"
  />
  <UDivider
    :ui="{
      label: 'text-yellow-500 dark:text-yellow-500 text-base',
      border: {
        base: 'border-yellow-200 dark:border-yellow-800',
      },
    }"
    type="solid"
    label="Secondi Piatti"
    size="xs"
    v-if="tableState[tableNumber - 1][2] === 'Busy'"
  />
  <UDivider
    :ui="{
      label: 'text-red-500 dark:text-red-500 text-base',
      border: {
        base: 'border-red-200 dark:border-red-800',
      },
    }"
    type="solid"
    label="Secondi Piatti"
    size="xs"
    v-if="tableState[tableNumber - 1][2] === 'Wait'"
  />
  <p class="my-2 font-thin italic">
    {{ secondiPiattiCount }}
    <template v-if="secondiPiattiCount === 1"> Second Course</template>
    <template v-else> Second Courses </template>
  </p>
  <UButtonGroup>
    <UButton
      @click="tableState[tableNumber - 1][2] = 'Wait'"
      class="m-0.5 mb-6"
      size="2xs"
      color="red"
      variant="soft"
    >
      Wait
    </UButton>
    <UButton
      @click="tableState[tableNumber - 1][2] = 'Busy'"
      class="m-0.5 mb-6"
      size="2xs"
      color="yellow"
      variant="soft"
    >
      Busy
    </UButton>
    <UButton
      @click="tableState[tableNumber - 1][2] = 'Done'"
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
const props = defineProps({
  secondiPiattiCount: {
    type: Number,
    required: true,
  },
  tableNumber: {
    type: Number,
    required: true,
  },
});

const { secondiPiattiCount } = props;
const tableState = useTableState();
</script>
