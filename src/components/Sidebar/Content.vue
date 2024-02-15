<template>
  <div class="h-full min-h-fit space-y-4 overflow-y-scroll">
    <div
      class="flex cursor-pointer items-center gap-2 rounded-r-2xl px-4 py-4 transition hover:bg-sky-800 hover:text-slate-200"
      :class="[isOpen ? 'w-64 justify-start' : 'justify-center']"
      v-for="page in pages"
      :key="page"
    >
      <SidebarItem
        :open="props.isOpen"
        :label="page.label"
        :children="page.children"
      >
        <template #icon>
          <component :is="page.icon" />
        </template>
      </SidebarItem>
    </div>
  </div>
</template>

<script setup>
import {
  ClipboardEdit,
  Factory,
  Gauge,
  LayoutDashboard,
  LibraryBig,
  Megaphone,
  SmartphoneNfc,
  UsersRound,
} from "lucide-vue-next";
import SidebarItem from "./SidebarItem.vue";

const props = defineProps(["isOpen"]);
const pages = [
  { label: "Dashboard", icon: LayoutDashboard },
  { label: "Última comunicação", icon: SmartphoneNfc },
  { label: "Supervisório", icon: Gauge },
  { label: "Revenda", icon: Factory },
  { label: "Clientes", icon: UsersRound },
  {
    label: "Equipamentos",
    icon: SmartphoneNfc,
    children: [
      { label: "Cadastro", icon: LibraryBig },
      { label: "Alertas", icon: Megaphone },
    ],
  },
  {
    label: "Relatório",
    icon: ClipboardEdit,
    children: [
      { label: "Consumo", icon: Megaphone },
      { label: "Individual", icon: LibraryBig },
    ],
  },
];
</script>
