<template>
  <div class="contacts__list">
    <ContactItem
      class="contact__item"
      v-for="contact in contacts"
      :key="contact.name"
      :contact="contact"
    />
  </div>
</template>

<script>
import ContactItem from "./ContactItem";
export default {
  name: "ContactsList",
  components: {
    ContactItem
  },
  props: ["contacts"]
};
</script>

<style lang="scss" scoped>
.contacts__list {
  position: sticky;
  top: 25px;
  left: 0;
}
</style>