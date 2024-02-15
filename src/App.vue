<template>
  <div class="flex min-h-full flex-col overflow-y-hidden">
    <Header />
    <div class="flex h-full flex-1">
      <Sidebar />
      <Main />
    </div>
  </div>
</template>

<script>
import Header from "@/components/Header/Header.vue";
import Main from "@/components/Main/Main.vue";
import Sidebar from "@/components/Sidebar/Sidebar.vue";

export default {
  components: {
    Header,
    Main,
    Sidebar,
  },
};
</script>
