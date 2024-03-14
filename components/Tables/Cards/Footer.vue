<template>
  <p class="font-thin italic">
    {{ plateCount }}
    <template v-if="plateCount === 1"> Plate </template>
    <template v-else> Plates </template>
  </p>
  <UButton
    icon="i-material-symbols:receipt-long-outline-rounded"
    size="sm"
    color="primary"
    variant="link"
    label="Ticket"
    :trailing="true"
  />
</template>

<script lang="ts" setup>
const props = defineProps({
  plateCount: {
    type: Number,
  },
  tableNumber: {
    type: Number,
    required: true,
  },
});

const { plateCount } = props;
</script>
