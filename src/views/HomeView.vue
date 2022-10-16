<template>
  <div class="home item_flex item_column_flex">
    <div class="height_block bg_color_black"></div>
    <header class="margin_around padding_around">
      <HeaderComponent />
    </header>
    <main class="margin_around padding_around">
      <MainComponent />
    </main>
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

export default {
  name: "HomeView",
  components: {
    HeaderComponent,
    MainComponent,
    FooterComponent,
  },
};
</script>
