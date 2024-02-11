<template>
  <UHorizontalNavigation
    :links="links"
    class="border-b border-gray-200 dark:border-gray-800"
  />
  <slot />
</template>

<script setup>
const route = useRoute();

const links = [
  [
    {
      label: "Home",
      icon: "i-heroicons-home",
      to: "/home",
    },
  ],
  [
    {
      label: "Tables",
      icon: "material-symbols:table-restaurant-outline-rounded",
      to: "/tables",
    },
  ],
  [
    {
      label: "Tickets",
      icon: "material-symbols:receipt-long-outline-rounded",
      to: "/tickets",
    },
  ],
  [
    {
      label: "Settings",
      icon: "ion:settings-outline",
      to: "/settings",
    },
  ],
];
</script>
