<template>
  <div class="item_flex item_column_flex">
    <div class="fixed_position_only">
      <SideNavigatorComponent />
    </div>
    <main>
      <MainMobileComponent />
    </main>
    <div>
      <!-- <FooterMobileComponent /> -->
    </div>
  </div>
</template>

<script>
import SideNavigatorComponent from "@/components/mobileNavigation/SideNavigatorComponent.vue";
import MainMobileComponent from "@/components/mobileMain/MainMobileComponent.vue";

export default {
  name: "MobileComponent",
  components: {
    SideNavigatorComponent,
    MainMobileComponent,
  },
  props: {},
  data() {
    return {};
  },
  created() {},
  methods: {},
};
</script>
