<template>
  <UContainer class="w-full mt-4 flex flex-wrap">
    <UCard
      class="min-w-56 max-w-80 mx-2 text-center"
      :ui="{
        background: 'bg-white dark:bg-gray-900',
        divide: 'divide-y divide-slate-200 dark:divide-slate-800',
        ring: 'ring-2 ring-primary-200 dark:ring-primary-800',
      }"
      v-for="(card, index) in cards"
    >
      <template #header>
        <p class="text-xl">Table {{ card.tableNumber }}</p>
        <p class="font-thin italic">
          {{ card.guestCount }}
          <template v-if="card.guestCount === 1">
            {{ description.guest.single }}
          </template>
          <template v-else>
            {{ description.guest.multiple }}
          </template>
        </p>
        <UBadge color="primary" variant="soft">Ready</UBadge>
      </template>
      <UDivider
        :ui="{ label: 'text-primary-500 dark:text-primary-400 text-base' }"
        type="dashed"
        label="Anti Pasti"
      />
      <p class="my-4 mb-2 font-thin italic">
        {{ card.antiPastiCount }}
        <template v-if="card.antiPastiCount === 1">
          {{ description.antiPasti.single }}
        </template>
        <template v-else>
          {{ description.antiPasti.multiple }}
        </template>
      </p>
      <UButton class="m-0.5 mb-6" size="2xs" color="red" variant="outline">
        Wait
      </UButton>
      <UButton class="m-0.5 mb-6" size="2xs" color="orange" variant="outline">
        Busy
      </UButton>
      <UButton class="m-0.5 mb-6" size="2xs" color="primary" variant="outline">
        Done
      </UButton>
      <UDivider
        :ui="{ label: 'text-primary-500 dark:text-primary-400 text-base' }"
        type="dashed"
        label="Primi Piatti"
      />
      <p class="my-4 font-thin italic">
        {{ card.primiPiattiCount }}
        <template v-if="card.primiPiattiCount === 1">
          {{ description.primiPiatti.single }}
        </template>
        <template v-else>
          {{ description.primiPiatti.multiple }}
        </template>
      </p>
      <UDivider
        :ui="{ label: 'text-primary-500 dark:text-primary-400 text-base' }"
        type="dashed"
        label="Secondi Piatti"
      />
      <p class="my-4 font-thin italic">
        {{ card.secondiPiattiCount }}
        <template v-if="card.secondiPiattiCount === 1">
          {{ description.secondiPiatti.single }}
        </template>
        <template v-else>
          {{ description.secondiPiatti.multiple }}
        </template>
      </p>
      <UDivider
        :ui="{ label: 'text-primary-500 dark:text-primary-400 text-base' }"
        type="dashed"
        label="Dolce"
      />
      <p class="mt-4 font-thin italic">
        {{ card.dolceCount }}
        <template v-if="card.dolceCount === 1">
          {{ description.dolce.single }}
        </template>
        <template v-else>
          {{ description.dolce.multiple }}
        </template>
      </p>

      <template #footer>
        <p class="font-thin italic">
          {{ totalPlatesPerTable(index) }}
          <template
            v-if="
              totalPlatesPerTable(index) >= 2 || totalPlatesPerTable(index) == 0
            "
          >
            {{ description.plates.multiple }}
          </template>
          <template v-else>
            {{ description.plates.single }}
          </template>
        </p>
      </template>
    </UCard>
  </UContainer>
</template>

<script setup lang="ts">
const description = {
  guest: {
    single: "Guest",
    multiple: "Guests",
  },
  antiPasti: {
    single: "Appetizer",
    multiple: "Appetizers",
  },
  primiPiatti: {
    single: "First Course",
    multiple: "First Courses",
  },
  secondiPiatti: {
    single: "Second Course",
    multiple: "Second Courses",
  },
  dolce: {
    single: "Dessert",
    multiple: "Desserts",
  },
  plates: {
    single: "Plate",
    multiple: "Plates",
  },
};

function totalPlatesPerTable(tableNumber: number): any {
  return (
    cards[tableNumber].antiPastiCount +
    cards[tableNumber].dolceCount +
    cards[tableNumber].primiPiattiCount +
    cards[tableNumber].secondiPiattiCount
  );
}

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
