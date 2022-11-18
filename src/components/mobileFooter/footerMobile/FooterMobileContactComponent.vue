<template>
  <div class="bg_gray">
    <div class="padding_arount_1">
      <h3>Зв'яжітся з нами</h3>
    </div>
    <div class="item_flex item_column_flex item_content_around margin_around">
      <div
        v-for="contact in listContacts"
        :key="contact.value"
        class="item_flex item_content_around padding_bottom_1"
      >
        <div>
          <img
            v-if="contact.value == 0"
            src="../../../assets/telegram.png"
            :alt="contact.text"
            width="26"
            height="26"
          />
          <img
            v-else-if="contact.value == 1"
            src="../../../assets/viber.png"
            :alt="contact.text"
            width="26"
            height="26"
          />
          <img
            v-else
            src="../../../assets/facebook.png"
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
      <div>
        <div v-for="cont in contacts" :key="cont.id" class="item_column_flex">
          <div v-if="cont.our_address" class="item_column_flex">
            <p>
              {{ cont.phone }}
            </p>
            <p>
              {{ cont.email }}
            </p>
            <p class="font_times_new_roman f_bold">
              {{ cont.our_address }}
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
        
<script>
export default {
  name: "FooterMobileContactComponent",
  props: {},
  data() {
    return {
      listContacts: null,
      contacts: null,
    };
  },
  created() {
    this.runGetData();
  },
  methods: {
    runGetData() {
      this.dataForContacts().then(() => this.getContactAndAddress());
    },
    async dataForContacts() {
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
    async getContactAndAddress() {
      // Get data contacts
      this.contacts = await fetch(
        `${this.$store.getters.getServerUrl}/contacts/`
      )
        .then((response) => response.json())
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