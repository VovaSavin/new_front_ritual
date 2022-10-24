<template>
  <div
    id="contact"
    class="item_flex item_content_between item_wrap f_family_abril"
  >
    <FooterContactComponent />
    <FooterNavigationComponent />
    <FooterTellMeComponent />
  </div>
</template>
    
<script>
import FooterContactComponent from "@/components/footer/FooterContactComponent.vue";
import FooterNavigationComponent from "@/components/footer/FooterNavigationComponent.vue";
import FooterTellMeComponent from "@/components/footer/FooterTellMeComponent.vue";

export default {
  name: "FooterComponent",
  components: {
    FooterContactComponent,
    FooterNavigationComponent,
    FooterTellMeComponent,
  },
  props: {},
  data() {
    return {};
  },
  created() {},
  methods: {},
};
</script>
    
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
    