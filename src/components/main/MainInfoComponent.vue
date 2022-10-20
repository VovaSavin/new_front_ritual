<template>
  <div class="item_flex item_content_around margin_t_3 margin_b_3">
    <div
      class="item_flex item_column_flex max_width_75"
      :class="{
        f_bold: infoTxt == 'Ж',
        f_italic: infoTxt == 'К',
        'f_bold f_italic': infoTxt == 'ЖК',
      }"
    >
      <div
        class="
          item_flex_inline item_vertical_base item_content_center
          f_family_abril
        "
      >
        <h2 class="case_up">Чому ми</h2>
        <h1>?</h1>
      </div>
      <div class="item_flex item_content_between text_left">
        <div class="f_family_abril font_18">
          {{ info }}
        </div>
      </div>
    </div>
    <div>
      <img
        src="../../assets/forMain.png"
        alt="mainImg"
        width="540"
        height="369"
      />
    </div>
  </div>
</template>
      
<script>
export default {
  name: "MainInfoComponent",
  props: {},
  data() {
    return {
      info: JSON.parse(localStorage.getItem("info"))[0].description_site,
      infoTxt: JSON.parse(localStorage.getItem("info"))[0].font,
    };
  },
  created() {},
  methods: {},
};
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>