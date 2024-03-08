<template>
  <UContainer class="w-full mt-4 flex flex-wrap">
    <UCard
      class="min-w-56 max-w-80 mx-2 text-center max-h-min"
      :ui="{
        background: 'bg-white dark:bg-gray-900',
        divide: 'divide-y divide-slate-200 dark:divide-slate-800',
        ring: 'ring-2 ring-primary-100 dark:ring-primary-900',
      }"
      v-for="(card, index) in cards"
    >
      <template #header>
        <TablesCardsHeader
          :table-number="card.tableNumber"
          :guest-count="card.guestCount"
        />
      </template>
      <TablesCardsAntiPasti
        :anti-pasti-count="card.antiPastiCount"
        :table-number="card.tableNumber"
        v-if="card.antiPastiCount > 0"
      />
      <TablesCardsPrimiPiatti :primi-piatti-count="card.primiPiattiCount" />
      <TablesCardsSecondiPiatti
        :secondi-piatti-count="card.secondiPiattiCount"
      />
      <TablesCardsDolce :dolce-count="card.primiPiattiCount" />

      <template #footer>
        <TablesCardsFooter
          :table-number="card.tableNumber"
          :plate-count="
            cards[index].antiPastiCount +
            cards[index].primiPiattiCount +
            cards[index].secondiPiattiCount +
            cards[index].dolceCount
          "
        />
      </template>
    </UCard>
  </UContainer>
</template>

<script setup lang="ts">
const tableState = useTableState();
const cards = [
  {
    tableNumber: 1,
    guestCount: 1,
    antiPastiCount: 1,
    primiPiattiCount: 1,
    secondiPiattiCount: 1,
    dolceCount: 1,
  },
  {
    tableNumber: 2,
    guestCount: 1,
    antiPastiCount: 0,
    primiPiattiCount: 1,
    secondiPiattiCount: 1,
    dolceCount: 1,
  },
  {
    tableNumber: 3,
    guestCount: 2,
    antiPastiCount: 1,
    primiPiattiCount: 2,
    secondiPiattiCount: 2,
    dolceCount: 1,
  },
  {
    tableNumber: 4,
    guestCount: 1,
    antiPastiCount: 0,
    primiPiattiCount: 0,
    secondiPiattiCount: 1,
    dolceCount: 0,
  },
  {
    tableNumber: 5,
    guestCount: 1,
    antiPastiCount: 0,
    primiPiattiCount: 0,
    secondiPiattiCount: 1,
    dolceCount: 0,
  },
];
</script>
