<template>
  <div
    @click="toUp()"
    class="item_fixed border_round w_70_px h_anchor cursor_point"
  >
    <div class="h-100">
      <span class="none_decoration black_color vertical_text">Вгору</span>
    </div>
  </div>
</template>
  
  <script>
export default {
  name: "AnchorComponent",
  components: {},
  data() {
    return {};
  },
  created() {},
  methods: {
    toUp() {
      // Go to up
      document.location.href = "#";
    },
  },
};
</script>
  
  <style scoped>
</style>
  