<template>
  <div>
    <div v-if="ifMobileDevice">
      <HomeMobile />
    </div>
    <div v-else class="home item_flex item_column_flex">
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
  </div>
</template>

<script>
// @ is an alias to /src
import HeaderComponent from "@/components/HeaderComponent.vue";
import MainComponent from "@/components/MainComponent.vue";
import FooterComponent from "@/components/FooterComponent.vue";
import AnchorComponent from "@/components/another/AnchorComponent.vue";
import HomeMobile from "@/views/HomeMobile.vue";

export default {
  name: "HomeView",
  components: {
    HeaderComponent,
    MainComponent,
    FooterComponent,
    AnchorComponent,
    HomeMobile,
  },
  data() {
    return {
      ifMobileDevice: false,
    };
  },
  created() {
    this.runnerListenResizeWindow();
  },
  methods: {
    async runnerListenResizeWindow() {
      // Run listener for resize window
      this.listenResizeWindow();
      this.changeDisplaySwitch();
    },
    listenResizeWindow() {
      // Прослушивает изменение окна браузера
      window.addEventListener("resize", this.changeDisplaySwitch);
    },
    changeDisplaySwitch() {
      // Меняет верхнюю навигацию сайта
      let tempSize = document.querySelector("body").offsetWidth;
      if (tempSize < 500) {
        this.ifMobileDevice = true;
      } else {
        this.ifMobileDevice = false;
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
