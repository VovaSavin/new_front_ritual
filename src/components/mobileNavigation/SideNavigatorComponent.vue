<template>
  <div class="item_flex item_column_flex bg_color_black">
    <div class="text_left" v-if="hideOrShow" id="side_navigate_close">
      <svg
        xmlns="http://www.w3.org/2000/svg"
        width="26"
        height="26"
        fill="black"
        id="show_hide_side_navi"
        class="bi bi-list cursor_point margin_around"
        viewBox="0 0 16 16"
        @click="changeStatusInnerSideMenu()"
      >
        <path
          fill-rule="evenodd"
          d="M2.5 12a.5.5 0 0 1 .5-.5h10a.5.5 0 0 1 0 1H3a.5.5 0 0 1-.5-.5zm0-4a.5.5 0 0 1 .5-.5h10a.5.5 0 0 1 0 1H3a.5.5 0 0 1-.5-.5zm0-4a.5.5 0 0 1 .5-.5h10a.5.5 0 0 1 0 1H3a.5.5 0 0 1-.5-.5z"
        />
      </svg>
    </div>
    <div
      v-else
      id="side_navigate"
      class="
        item_flex item_column_flex item_vertical_base
        font_times_new_roman font_20
        text_left
      "
    >
      <div class="w-100 text_right">
        <svg
          id="close_btn"
          xmlns="http://www.w3.org/2000/svg"
          width="28"
          height="28"
          fill="black"
          class="bi bi-x-lg cursor_point margin_around"
          viewBox="0 0 16 16"
          @click="changeStatusInnerSideMenu()"
        >
          <path
            fill-rule="evenodd"
            d="M13.854 2.146a.5.5 0 0 1 0 .708l-11 11a.5.5 0 0 1-.708-.708l11-11a.5.5 0 0 1 .708 0Z"
          />
          <path
            fill-rule="evenodd"
            d="M2.146 2.146a.5.5 0 0 0 0 .708l11 11a.5.5 0 0 0 .708-.708l-11-11a.5.5 0 0 0-.708 0Z"
          />
        </svg>
      </div>

      <div>
        <ul class="none_decoration case_up">
          <li v-for="nav in navigation" :key="nav.value" class="margin_around">
            <a
              class="none_decoration black_color"
              :href="nav.link"
              style="padding: 10px 2px"
              @click="changeStatusInnerSideMenu()"
            >
              {{ nav.text }}
            </a>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>
  
  <script>
export default {
  name: "SideNavigatorComponent",
  components: {},
  props: {},
  data() {
    return {
      hideOrShow: true,
      navigation: JSON.parse(localStorage.getItem("navigation")),
    };
  },
  created() {},
  methods: {
    changeStatusInnerSideMenu() {
      // Change statusInnerSideMenu
      this.hideOrShow = !this.hideOrShow;
    },
  },
};
</script>