<template>
  <div class="home item_flex item_column_flex">
    <div class="height_block bg_color_black"></div>
    <header class="margin_around padding_around">
      <HeaderComponent />
    </header>
    <main class="margin_around padding_around">
      <MainComponent />
    </main>
    <button @click="qwe()">Click</button>
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

export default {
  name: "HomeView",
  components: {
    HeaderComponent,
    MainComponent,
    FooterComponent,
  },
  data() {
    return {};
  },
  created() {},
  methods: {
    qwe() {
      if (document.URL !== "http://localhost:8080/#/") {
        this.$router.push({ name: "home" });
      } else {
        console.log("The");
        console.log(document.URL);
      }
    },
  },
};
</script>

<style scoped>
.line_under_block {
  border-bottom: 1px solid gray;
  margin: 1.1rem;
}
</style>
