<template>
  <UContainer class="mt-8 bg-slate-primary">
    <UTable
      :rows="rows"
      :columns="colums"
      :ui="{
        tr: { size: 'text-lg font-normal' },
        th: { size: 'text-lg font-normal' },
        td: { size: 'text-lg font-normal' },
      }"
    >
    </UTable>
  </UContainer>
  <UContainer class="flex justify-center">
    <UPagination v-model="page" :total="items.length" />
  </UContainer>
</template>

<script setup lang="ts">
const page = ref(1);
const items = ref(Array(55));
const colums = [
  {
    key: "id",
    label: "ID",
  },
  {
    key: "name",
    label: "User name",
  },
  {
    key: "title",
    label: "Job position",
  },
  {
    key: "email",
    label: "Email",
  },
  {
    key: "role",
    label: "Role",
  },
];

const rows = [
  {
    id: 1,
    name: "Lindsay Walton",
    title: "Front-end Developer",
    email: "lindsay.walton@example.com",
    role: "Member",
  },
  {
    id: 2,
    name: "Courtney Henry",
    title: "Designer",
    email: "courtney.henry@example.com",
    role: "Admin",
  },
  {
    id: 3,
    name: "Tom Cook",
    title: "Director of Product",
    email: "tom.cook@example.com",
    role: "Member",
  },
  {
    id: 4,
    name: "Whitney Francis",
    title: "Copywriter",
    email: "whitney.francis@example.com",
    role: "Admin",
  },
  {
    id: 5,
    name: "Leonard Krasner",
    title: "Senior Designer",
    email: "leonard.krasner@example.com",
    role: "Owner",
  },
  {
    id: 6,
    name: "Floyd Miles",
    title: "Principal Designer",
    email: "floyd.miles@example.com",
    role: "Member",
  },
];
</script>
