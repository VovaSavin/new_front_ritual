<template>
  <div class="bg_gray_darkness">
    <div class="padding_arount_1">
      <h3>Напишіть нам</h3>
    </div>
    <div>
      <form
        class="item_flex item_column_flex margin_around"
        action="#"
        @submit="sendMail"
      >
        <input
          class="mb-2"
          type="email"
          name="e_mail"
          id="e_mail"
          cols="30"
          placeholder="Пошта..."
          v-model="letterMail.mails"
          required="true"
        />
        <textarea
          class=""
          name="txt"
          id="txt"
          cols="30"
          rows="5"
          placeholder="Текст повідомлення..."
          v-model="letterMail.text"
          required="true"
        ></textarea>
        <input class="margin_around" type="submit" value="Відправити" />
      </form>
    </div>
  </div>
</template>
        
<script>
import axios from "axios";
export default {
  name: "FooterMobileTellMeComponent",
  props: {},
  data() {
    return {
      letterMail: {
        mails: null,
        text: null,
      },
    };
  },
  created() {},
  methods: {
    async sendMail(e) {
      // Forming JSON for send letter to mail
      e.preventDefault();
      await axios({
        url: `${this.$store.getters.getServerUrl}/send_mail/`,
        method: "post",
        headers: {
          accept: "application/json",
          "Content-Type": "application/json",
        },
        data: JSON.stringify(this.letterMail),
      })
        .then(function (response) {
          console.log(response);
          alert("Лист відправлено!");
          location.reload();
        })
        .catch(function (error) {
          console.log(error);
        });
    },
  },
};
</script>
        
    <!-- Add "scoped" attribute to limit CSS to this component only -->
    <style scoped>
</style>