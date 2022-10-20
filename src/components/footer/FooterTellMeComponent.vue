<template>
  <div class="bg_gray width_30_per">
    <div class="padding_bottom_1">
      <h3>Напишіть нам</h3>
    </div>
    <div>
      <form class="item_flex item_column_flex margin_around" action="#">
        <input
          class="mb-2"
          type="email"
          name="e_mail"
          id="e_mail"
          cols="30"
          placeholder="Пошта..."
        />
        <textarea
          class=""
          name="txt"
          id="txt"
          cols="30"
          rows="5"
          placeholder="Текст повідомлення..."
        ></textarea>
        <input class="margin_around" type="submit" value="Відправити" />
      </form>
    </div>
  </div>
</template>
      
  <script>
export default {
  name: "FooterTellMeComponent",
  props: {},
  data() {
    return {};
  },
  created() {},
  methods: {},
};
</script>
      
  <!-- Add "scoped" attribute to limit CSS to this component only -->
  <style scoped>
</style>