<template>
  <UHorizontalNavigation
    :links="links"
    class="border-b border-slate-200 dark:border-slate-800"
    :ui="{ label: 'text-lg font-normal' }"
  />
  <slot />
</template>

<script setup>
const links = [
  [],
  [
    {
      label: "Home",
      icon: "i-heroicons-home",
      to: "/",
    },
  ],
  [
    {
      label: "Tables",
      icon: "i-material-symbols:table-restaurant-outline-rounded",
      to: "/tables",
    },
  ],
  [
    {
      label: "Tickets",
      icon: "i-material-symbols:receipt-long-outline-rounded",
      to: "/tickets",
    },
  ],
  [
    {
      label: "Settings",
      icon: "i-ion:settings-outline",
      to: "/settings",
    },
  ],
  [],
];
</script>
