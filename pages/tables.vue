<template>
  <UContainer class="flex flex-wrap">
    <UCard class="min-w-64 max-w-80 m-4 text-center" v-for="card in cards">
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
      </template>
      <UDivider
        :ui="{ label: 'text-primary-500 dark:text-primary-400 text-base' }"
        type="dashed"
        label="Anti Pasti"
      />
      <p class="mb-4 font-thin italic">
        {{ card.antiPastiCount }}
        <template v-if="card.antiPastiCount === 1">
          {{ description.antiPasti.single }}
        </template>
        <template v-else>
          {{ description.antiPasti.multiple }}
        </template>
      </p>
      <UDivider
        :ui="{ label: 'text-primary-500 dark:text-primary-400 text-base' }"
        type="dashed"
        label="Primi Piatti"
      />
      <p class="mb-4 font-thin italic">
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
      <p class="mb-4 font-thin italic">
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
      <p class="font-thin italic">
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
          {{
            card.antiPastiCount +
            card.primiPiattiCount +
            card.secondiPiattiCount +
            card.dolceCount
          }}
          <template
            v-if="
              card.antiPastiCount +
                card.primiPiattiCount +
                card.secondiPiattiCount +
                card.dolceCount >=
                2 ||
              card.antiPastiCount +
                card.primiPiattiCount +
                card.secondiPiattiCount +
                card.dolceCount ==
                0
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
const cards = ref([
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
]);
</script>
