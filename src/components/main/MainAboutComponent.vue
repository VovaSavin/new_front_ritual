<template>
  <div
    id="about"
    class="item_flex item_column_flex font_times_new_roman padding_around"
  >
    <div class="item_flex">
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
          <div v-for="we in about" :key="we.id">
            <div
              class="carousel-item"
              :class="{
                active: we.id == about[0].id,
                '': we.id != about[0].id,
              }"
            >
              <div
                class="item_flex item_content_around padding_around"
                :class="{ item_flex_reverse: we.id % 2 == 0 }"
              >
                <div class="">
                  <img
                    :src="we.picture"
                    class="services__image max_width_5 m_height_5"
                    :alt="we.name"
                    width="355"
                    height="255"
                  />
                </div>
                <div class="goods_visibility w-50">
                  <h3 class="">
                    {{ we.name }}
                  </h3>
                  <p
                    class="
                      f_bold
                      font_18
                      text_al_justify
                      padding_around padding_r_3 padding_l_3
                    "
                  >
                    {{ we.description }}
                  </p>
                </div>
              </div>
            </div>
          </div>
        </div>
        <button
          class="carousel-control-prev"
          type="button"
          data-bs-target="#carouselExampleControlsA"
          data-bs-slide="prev"
        >
          <span class="carousel-control-prev-icon" aria-hidden="true"></span>
          <span class="visually-hidden">Previous</span>
        </button>
        <button
          class="carousel-control-next"
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
  name: "MainAboutComponent",
  props: {},
  data() {
    return {
      nameSection: "?????? ??????",
      about: JSON.parse(localStorage.getItem("about")),
    };
  },
  created() {},
  methods: {},
};
</script>
        
        <!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.goods_visibility {
  opacity: 0.6;
}
.goods_visibility:hover {
  opacity: 1;
}
.services__image::before {
  content: "";
  position: absolute;
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
}
.d-line-wrap {
  display: flex;
  flex-direction: column-reverse;
}
.services__button {
  position: absolute;
  left: 12.5%;
  top: 16%;
  width: 75%;
  height: 70%;
  opacity: 0;
  z-index: 10;
  background: transparent;
  -webkit-transition: all 0.3s ease-out;
  -o-transition: all 0.3s ease-out;
  transition: all 0.3s ease-out;
}
.services__button:hover {
  opacity: 1;
  background: rgba(70, 70, 70, 0.596);
}
.align-center {
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  justify-content: center;
}
.d-flex {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: horizontal;
  -webkit-box-direction: normal;
  -ms-flex-flow: row wrap;
  flex-flow: row wrap;
  align-items: center;
}
button:hover {
  background-color: rgba(128, 128, 128, 0.459);
}
</style>