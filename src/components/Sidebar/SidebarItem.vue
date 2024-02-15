<template>
  <Disclosure v-if="hasChildren">
    <div class="">
      <DisclosureButton class="flex items-center gap-2">
        <slot name="icon"></slot>
        <span class="text-sm" v-if="open">{{ label }}</span>
      </DisclosureButton>
      <DisclosurePanel class="text-gray-500"> Items </DisclosurePanel>
    </div>
  </Disclosure>
  <div class="flex items-center gap-2" v-else>
    <slot name="icon"></slot>
    <span class="text-sm" v-if="open">{{ label }}</span>
  </div>
</template>

<script>
import { Disclosure, DisclosureButton, DisclosurePanel } from "@headlessui/vue";

export default {
  name: "SidebarItem",
  components: {
    Disclosure,
    DisclosureButton,
    DisclosurePanel,
  },
  props: {
    label: {
      type: String,
      required: true,
    },
    open: {
      type: Boolean,
      required: true,
    },
    children: {
      type: Object,
      required: false,
    },
  },
  computed: {
    hasChildren() {
      return this.children?.length > 0;
    },
  },
};
</script>
