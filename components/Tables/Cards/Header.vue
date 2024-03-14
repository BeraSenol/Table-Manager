<template>
  <p class="text-xl">Table {{ tableNumber }}</p>
  <p class="font-thin italic my-1">
    <template v-if="guestCount === 1"> 1 Guest </template>
    <template v-else> {{ guestCount }} Guests</template>
  </p>
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
