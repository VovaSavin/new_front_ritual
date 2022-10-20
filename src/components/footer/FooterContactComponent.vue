<template>
  <div class="bg_gray item_place">
    <h2>Зв'яжітся з нами</h2>
    <div class="item_column_flex item_content_around">
      <div
        v-for="contact in listContacts"
        :key="contact.value"
        class="item_flex item_content_around"
      >
        <div>
          <img
            v-if="contact.value == 0"
            src="../../assets/telegram.png"
            :alt="contact.text"
            width="26"
            height="26"
          />
          <img
            v-else-if="contact.value == 1"
            src="../../assets/viber.png"
            :alt="contact.text"
            width="26"
            height="26"
          />
          <img
            v-else
            src="../../assets/facebook.png"
            :alt="contact.text"
            width="26"
            height="26"
          />
        </div>
        <div class="w-50">
          <p>
            {{ contact.text }}
          </p>
        </div>
      </div>
    </div>
  </div>
</template>
      
<script>
export default {
  name: "FooterContactComponent",
  props: {},
  data() {
    return {
      listContacts: null,
    };
  },
  created() {
    this.dataForContacts();
  },
  methods: {
    dataForContacts() {
      // Some data for contacts
      this.listContacts = [
        {
          value: 0,
          text: "Telegram",
        },
        {
          value: 1,
          text: "Viber",
        },
        {
          value: 2,
          text: "Facebook",
        },
      ];
    },
  },
};
</script>
      
  <!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>