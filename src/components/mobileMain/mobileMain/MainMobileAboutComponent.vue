<template>
  <div
    id="about"
    class="item_flex item_column_flex font_times_new_roman margin_around"
  >
    <div class="item_flex item_column_flex">
      <div
        id="carouselExampleControlsA"
        class="
          item_flex item_content_between
          carousel
          slide
          w-100
          margin_b_3 margin_t_3
        "
        data-bs-ride="carousel"
      >
        <div class="carousel-inner">
          <div v-for="good in about" :key="good.id">
            <div
              class="carousel-item"
              :class="{
                active: good.id == about[0].id,
                '': good.id != about[0].id,
              }"
            >
              <div
                class="
                  item_flex item_column_flex item_content_around
                  padding_around
                "
                :class="{ item_flex_reverse: good.id % 2 == 0 }"
              >
                <div class="">
                  <img
                    :src="good.picture"
                    class="services__image"
                    :alt="good.name"
                    width="355"
                    height="255"
                  />
                </div>
                <div class="goods_visibility padding_around">
                  <h3 class="">
                    {{ good.name }}
                  </h3>
                  <p class="font_18 text_al_justify padding_around">
                    {{ good.description }}
                  </p>
                </div>
              </div>
            </div>
          </div>
        </div>
        <button
          class="carousel-control-prev bg_gray_transparent w_50_px"
          type="button"
          data-bs-target="#carouselExampleControlsA"
          data-bs-slide="prev"
        >
          <span class="carousel-control-prev-icon" aria-hidden="true"></span>
          <span class="visually-hidden">Previous</span>
        </button>
        <button
          class="carousel-control-next bg_gray_transparent w_50_px"
          type="button"
          data-bs-target="#carouselExampleControlsA"
          data-bs-slide="next"
        >
          <span class="carousel-control-next-icon" aria-hidden="true"></span>
          <span class="visually-hidden">Next</span>
        </button>
      </div>
    </div>
  </div>
</template>
        
  <script>
export default {
  name: "MainMobileAboutComponent",
  components: {},
  props: {},
  data() {
    return {
      nameSection: "?????? ??????",
      about: JSON.parse(localStorage.getItem("about")),
    };
  },
  props: {},
  created() {},
  methods: {},
};
</script>
        
        <!-- Add "scoped" attribute to limit CSS to this component only -->
    <style scoped>
</style>
        