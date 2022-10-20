<template>
  <div class="item_flex item_content_between">
    <div class="item_flex_inline width_50_percent text_left">
      <div>
        <img src="../assets/logo1.png" alt="logo" width="90" height="90" />
      </div>
      <div class="item_flex item_column_reverse_flex padding_bottom_04">
        <em class="opacity_05 font_14"> послуги </em>
        <b class="font_times_new_roman font_18">Ритуальні</b>
      </div>
    </div>
    <div class="width_50_percent">
      <ul class="item_flex item_content_between case_up none_decoration">
        <li v-for="navi in navigation" :key="navi.value">
          <a
            class="none_decoration black_color f_family_abril"
            :href="navi.link"
          >
            {{ navi.text }}
          </a>
        </li>
      </ul>
    </div>
  </div>
</template>
  
<script>
export default {
  name: "HeaderComponent",
  props: {},
  data() {
    return {
      navigation: null,
      info: null,
      goods: null,
      services: null,
      about: null,
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
        .then(() => this.setInToLocalStorage("about", this.about));
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
        { value: 1, text: "Товари", link: "#" },
        { value: 2, text: "Послуги", link: "#" },
        { value: 3, text: "Про нас", link: "#" },
        { value: 4, text: "Контакти", link: "#" },
      ];
    },
  },
};
</script>
  
  <!-- Add "scoped" attribute to limit CSS to this component only -->
  <style scoped>
</style>
  