<template>
  <p class="text-xl">Table {{ tableNumber }}</p>
  <p class="font-thin italic my-1">
    <template v-if="guestCount === 1"> 1 Guest </template>
    <template v-else> {{ guestCount }} Guests</template>
  </p>
  <UBadge
    v-if="tableState[tableNumber - 1] === 'Wait'"
    color="red"
    variant="soft"
  >
    Wait
  </UBadge>
  <UBadge
    v-if="tableState[tableNumber - 1] === 'Busy'"
    color="orange"
    variant="soft"
  >
    Busy
  </UBadge>
  <UBadge
    v-if="tableState[tableNumber - 1] === 'Done'"
    color="primary"
    variant="soft"
  >
    Ready
  </UBadge>
</template>

<script lang="ts" setup>
const props = defineProps({
  tableNumber: {
    type: Number,
    required: true,
  },
  guestCount: {
    type: Number,
    required: true,
  },
});
const { tableNumber, guestCount } = props;
const tableState = useTableState();
</script>
