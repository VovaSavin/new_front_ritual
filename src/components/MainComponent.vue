<template>
  <div class="item_flex item_column_flex">
    <MainInfoComponent />
    <div class="height_block_separator"></div>
    <MainGoodsComponent />
    <div class="height_block_separator"></div>
    <MainServicesComponent />
    <div class="height_block_separator"></div>
    <MainAboutComponent />
  </div>
</template>
    
<script>
import MainInfoComponent from "@/components/main/MainInfoComponent.vue";
import MainGoodsComponent from "@/components/main/MainGoodsComponent.vue";
import MainServicesComponent from "@/components/main/MainServicesComponent.vue";
import MainAboutComponent from "@/components/main/MainAboutComponent.vue";

export default {
  name: "MainComponent",
  components: {
    MainInfoComponent,
    MainGoodsComponent,
    MainServicesComponent,
    MainAboutComponent,
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
    