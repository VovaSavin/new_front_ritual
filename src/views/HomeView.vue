<template>
  <div class="home item_flex item_column_flex">
    <div class="height_block bg_color_black"></div>
    <AnchorComponent />
    <header class="margin_around padding_around">
      <HeaderComponent />
    </header>
    <main class="margin_around padding_around">
      <MainComponent />
    </main>
    <div class="line_under_block margin_around"></div>
    <footer class="margin_around padding_around">
      <FooterComponent />
    </footer>
  </div>
</template>

<script>
// @ is an alias to /src
import HeaderComponent from "@/components/HeaderComponent.vue";
import MainComponent from "@/components/MainComponent.vue";
import FooterComponent from "@/components/FooterComponent.vue";
import AnchorComponent from "@/components/another/AnchorComponent.vue";

export default {
  name: "HomeView",
  components: {
    HeaderComponent,
    MainComponent,
    FooterComponent,
    AnchorComponent,
  },
  data() {
    return {};
  },
  created() {},
  methods: {},
};
</script>

<style scoped>
.line_under_block {
  border-bottom: 1px solid gray;
  margin: 1.1rem;
}
</style>
