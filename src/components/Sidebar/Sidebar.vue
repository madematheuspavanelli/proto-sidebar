<template>
  <div
    class="relative h-[calc(100vh-3.5rem)] bg-light-blue shadow-xl transition-all duration-300"
    :class="[isOpen ? 'w-64' : 'w-16']"
  >
    <button
      @click="toggleOpen()"
      class="absolute right-0 top-6 translate-x-1/2 cursor-pointer rounded-full p-1"
    >
      <ArrowRightCircle
        @click.stop="toggleOpen()"
        class="cursor-pointer rounded-full bg-white transition"
        :class="{ 'rotate-180': isOpen }"
      />
    </button>

    <div class="relative flex h-full w-full flex-col overflow-x-hidden py-12">
      <Content :isOpen="isOpen" />
      <Metam v-show="isOpen" class="mx-auto" />
    </div>
  </div>
</template>

<script setup>
import { useToggle } from "@vueuse/core";
import { ArrowRightCircle } from "lucide-vue-next";
import Metam from "@/assets/icons/Metam.vue";
import Content from "./Content.vue";

const [isOpen, toggleOpen] = useToggle();
</script>
