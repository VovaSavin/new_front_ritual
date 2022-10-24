<template>
  <div class="item_flex item_column_flex margin_t_3">
    <MainMobileInfoComponent />
    <div class="height_block_separator"></div>
    <MainMobileGoodsComponent />
    <div class="height_block_separator"></div>
    <MainMobileServicesComponent />
    <div class="height_block_separator"></div>
    <MainMobileAboutComponent />
  </div>
</template>
      
<script>
import MainMobileInfoComponent from "@/components/mobileMain/mobileMain/MainMobileInfoComponent.vue";
import MainMobileGoodsComponent from "@/components/mobileMain/mobileMain/MainMobileGoodsComponent.vue";
import MainMobileServicesComponent from "@/components/mobileMain/mobileMain/MainMobileServicesComponent.vue";
import MainMobileAboutComponent from "@/components/mobileMain/mobileMain/MainMobileAboutComponent.vue";

export default {
  name: "MainMobileComponent",
  components: {
    MainMobileInfoComponent,
    MainMobileGoodsComponent,
    MainMobileServicesComponent,
    MainMobileAboutComponent,
  },
  props: {},
  data() {
    return {
      info: null,
    };
  },
  props: {},
  created() {},
  methods: {},
};
</script>
      
      <!-- Add "scoped" attribute to limit CSS to this component only -->
  <style scoped>
</style>
      