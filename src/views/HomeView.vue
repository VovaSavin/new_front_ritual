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
    this.runApp();
  },
  methods: {
    runApp() {
      this.listNavigation()
        .then(() => this.getMainInfo())
        .then(() => this.setInToLocalStorage("info", this.info))
        .then(() => this.getInfoAboutGoods())
        .then(() => this.setInToLocalStorage("goods", this.goods))
        .then(() => this.getInfoAboutServices())
        .then(() => this.setInToLocalStorage("services", this.services))
        .then(() => this.getAboutUs())
        .then(() => this.setInToLocalStorage("about", this.about))
        .then(() => this.setInToLocalStorage("navigation", this.navigation))
        .then(() => this.runnerListenResizeWindow());
    },
    async getMainInfo() {
      // Get info from backend
      this.info = await fetch(`${this.$store.getters.getServerUrl}/main_img/`)
        .then((response) => response.json())
        .catch(function (error) {
          console.log(error);
        });
    },
    async getInfoAboutGoods() {
      // Get data from BackEnd
      this.goods = await fetch(
        `${this.$store.getters.getServerUrl}/rith_goods/`
      )
        .then((response) => response.json())
        .catch(function (error) {
          console.log(error);
        });
    },
    async getInfoAboutServices() {
      // Get data from BackEnd
      this.services = await fetch(
        `${this.$store.getters.getServerUrl}/rith_services/`
      )
        .then((response) => response.json())
        .catch(function (error) {
          console.log(error);
        });
    },
    async getAboutUs() {
      // Get info about owner site
      this.about = await fetch(`${this.$store.getters.getServerUrl}/about/`)
        .then((response) => response.json())
        .catch(function (error) {
          console.log(error);
        });
    },
    async setInToLocalStorage(nameInStorage, parametr) {
      // Instance value in to local storage
      localStorage.setItem(nameInStorage, JSON.stringify(parametr));
    },
    async listNavigation() {
      // Return data-oject with list navigation
      this.navigation = [
        { value: 0, text: "Головна", link: "#" },
        { value: 1, text: "Товари", link: "#goods" },
        { value: 2, text: "Послуги", link: "#services" },
        { value: 3, text: "Про нас", link: "#about" },
        { value: 4, text: "Контакти", link: "#contact" },
      ];
    },

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
