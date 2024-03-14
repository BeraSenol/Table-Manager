<template>
  <UContainer class="w-full mt-4 flex flex-wrap">
    <UCard
      class="min-w-56 max-w-80 mx-2 text-center max-h-min"
      :ui="{
        background: 'bg-white dark:bg-slate-950',
        divide: 'divide-y divide-primary-200 dark:divide-primary-800',
        ring: 'ring-primary-100 dark:ring-primary-900',
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
      <TablesCardsPrimiPiatti
        :primi-piatti-count="card.primiPiattiCount"
        :table-number="card.tableNumber"
        v-if="card.primiPiattiCount > 0"
      />
      <TablesCardsSecondiPiatti
        :secondi-piatti-count="card.secondiPiattiCount"
        :table-number="card.tableNumber"
        v-if="card.secondiPiattiCount > 0"
      />
      <TablesCardsDolce
        :dolce-count="card.primiPiattiCount"
        :table-number="card.tableNumber"
        v-if="card.dolceCount > 0"
      />

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
    antiPastiState: "",
    primiPiattiState: "",
    secondiPiattiState: "",
    dolceState: "",
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
    guestCount: 5,
    antiPastiCount: 0,
    primiPiattiCount: 5,
    secondiPiattiCount: 5,
    dolceCount: 3,
  },
];
</script>
