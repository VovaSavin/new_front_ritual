<template>
  <div
    id="services"
    class="item_flex item_column_flex font_times_new_roman margin_around"
  >
    <div class="item_flex item_column_flex">
      <div
        id="carouselExampleControlsS"
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
          <div v-for="service in services" :key="service.id">
            <div
              class="carousel-item"
              :class="{
                active: service.id == services[0].id,
                '': service.id != services[0].id,
              }"
            >
              <div
                class="
                  item_flex item_column_flex item_content_around
                  padding_around
                "
                :class="{ item_flex_reverse: service.id % 2 == 0 }"
              >
                <div class="">
                  <img
                    :src="service.picture"
                    class="services__image"
                    :alt="service.name"
                    width="355"
                    height="255"
                  />
                </div>
                <div class="goods_visibility padding_around">
                  <h3 class="">
                    {{ service.name }}
                  </h3>
                  <p class="font_18 text_al_justify padding_around">
                    {{ service.description }}
                  </p>
                  <section class="pb-3 prices">
                    <div class="my-container">
                      <div class="row m-0">
                        <div class="item_flex item_content_center prices-table">
                          <table>
                            <tbody>
                              <tr>
                                <td>
                                  Від <b>{{ service.price_of }}</b> грн
                                </td>
                              </tr>
                            </tbody>
                          </table>
                        </div>
                      </div>
                    </div>
                  </section>
                </div>
              </div>
            </div>
          </div>
        </div>
        <button
          class="carousel-control-prev bg_gray_transparent w_50_px"
          type="button"
          data-bs-target="#carouselExampleControlsS"
          data-bs-slide="prev"
        >
          <span class="carousel-control-prev-icon" aria-hidden="true"></span>
          <span class="visually-hidden">Previous</span>
        </button>
        <button
          class="carousel-control-next bg_gray_transparent w_50_px"
          type="button"
          data-bs-target="#carouselExampleControlsS"
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
  name: "MainMobileServicesComponent",
  components: {},
  props: {},
  data() {
    return {
      nameSection: "Ритуальні послуги",
      services: JSON.parse(localStorage.getItem("services")),
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
        