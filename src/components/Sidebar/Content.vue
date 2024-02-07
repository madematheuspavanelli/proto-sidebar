<template>
  <div class="h-full space-y-4">
    <div
      class="flex cursor-pointer items-center gap-2 rounded-r-2xl px-4 py-4 transition hover:bg-sky-800 hover:text-slate-200"
      :class="[isOpen ? 'w-64 justify-start' : 'justify-center']"
      v-for="page in pages"
      :key="page"
    >
      <component :is="page.icon" />
      <span v-if="isOpen" class="text-sm">{{ page.label }}</span>
    </div>
  </div>
</template>

<script setup>
import { LayoutDashboard, SmartphoneNfc } from "lucide-vue-next";

const props = defineProps(["isOpen"]);
const pages = [
  { label: "Dashboard", icon: LayoutDashboard },
  { label: "Última comunicação", icon: SmartphoneNfc },
  { label: "Supervisório", icon: SmartphoneNfc },
  { label: "Revenda", icon: SmartphoneNfc },
  { label: "Clientes", icon: SmartphoneNfc },
  { label: "Equipamentos", icon: SmartphoneNfc },
  { label: "Relatório", icon: SmartphoneNfc },
];
</script>
