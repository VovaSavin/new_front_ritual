<template>
  <div class="bg_darkgray item_column_flex">
    <div class="padding_arount_1">
      <h3>Навіцація</h3>
    </div>
    <div class="">
      <ul
        class="
          item_flex item_column_flex item_content_between
          case_up
          none_decoration
          padding_0
        "
      >
        <li
          class="padding_bottom_1"
          v-for="navi in navigation"
          :key="navi.value"
        >
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
  name: "FooterMobileNavigationComponent",
  props: {},
  data() {
    return {
      navigation: JSON.parse(localStorage.getItem("navigation")),
    };
  },
  created() {},
  methods: {},
};
</script>
        
    <!-- Add "scoped" attribute to limit CSS to this component only -->
  <style scoped>
</style>