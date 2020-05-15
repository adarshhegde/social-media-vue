<template>
  <div class="right__sidebar">
    <h1>Contacts</h1>
    <ContactsList :contacts="contacts" />
  </div>
</template> 

<script>
import ContactsList from "./reusable/ContactsList";
export default {
  name: "LeftNavigation",
  components: {
    ContactsList
  },
  data: function() {
    return {
      contacts: [
        {
          name: "Manoj Pawar SJ",
          profile_picture:
            "https://scontent-maa2-1.xx.fbcdn.net/v/t1.0-9/95425115_1644661215684137_5586577808605315072_n.jpg?_nc_cat=111&_nc_sid=09cbfe&_nc_ohc=2mHzP2Elhl0AX8WsKN3&_nc_ht=scontent-maa2-1.xx&oh=9dcfe34f13b03daf03dec8bcdd54b2cb&oe=5EE17FE6",
          active: true,
          last_seen: "Active Now"
        },
        {
          name: "Pracheta Nayak",
          profile_picture:
            "https://scontent-maa2-1.xx.fbcdn.net/v/t1.0-9/88112651_506236330316633_8396622146981330944_o.jpg?_nc_cat=110&_nc_sid=09cbfe&_nc_ohc=QMc_isAFiegAX_3fg-c&_nc_ht=scontent-maa2-1.xx&oh=ab0426f21ed6b0e3ea6a7e57237b0be2&oe=5EE339DB",
          active: false,
          last_seen: "2 days ago"
        },
        {
          name: "Soni Sins",
          profile_picture:
            "https://scontent-maa2-1.xx.fbcdn.net/v/t1.0-9/91837903_2729789473909421_4657730361353043968_o.jpg?_nc_cat=101&_nc_sid=09cbfe&_nc_ohc=6h0bxPrkI6kAX_yxrC8&_nc_ht=scontent-maa2-1.xx&oh=de6c152620e0538749f902557176d6d3&oe=5EE3E890",
          active: false,
          last_seen: "2 days ago"
        }
      ]
    };
  }
};
</script>

<style lang="scss" scoped>
.right__sidebar {
  h1 {
    color: #353535;
    font-size: 22px;
    line-height: 36px;
    letter-spacing: -0.5004pt;
    font-weight: 400;
    margin: 20px 14px;
    margin-bottom: 0;
    filter: var(--text-filter);
    transition: 0.3s cubic-bezier(0.4, 0, 0.2, 1) all;
  }
}
</style>