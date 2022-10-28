<template>
  <div
    id="contact"
    class="item_flex item_column_flex margin_t_3 item_content_around"
  >
    <div class="">
      <FooterMobileContactComponent />
    </div>
    <div class="">
      <FooterMobileTellMeComponent />
    </div>
    <div class="">
      <FooterMobileNavigationComponent />
    </div>
  </div>
</template>
        
<script>
import FooterMobileContactComponent from "@/components/mobileFooter/footerMobile/FooterMobileContactComponent.vue";
import FooterMobileNavigationComponent from "@/components/mobileFooter/footerMobile/FooterMobileNavigationComponent.vue";
import FooterMobileTellMeComponent from "@/components/mobileFooter/footerMobile/FooterMobileTellMeComponent.vue";

export default {
  name: "FooterMobileComponent",
  components: {
    FooterMobileContactComponent,
    FooterMobileNavigationComponent,
    FooterMobileTellMeComponent,
  },
  props: {},
  data() {
    return {};
  },
  props: {},
  created() {},
  methods: {},
};
</script>
        
        <!-- Add "scoped" attribute to limit CSS to this component only -->
    <style scoped>
</style>
        