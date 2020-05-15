<template>
  <div>
    <span class="contact__item__picture" :class="contact.active ? 'online' : 'offline'">
      <img :src="contact.profile_picture" />
    </span>
    <div class="contact__item__details">
      <span class="contact__item__name">{{contact.name}}</span>
      <span class="contact__item__lastseen">{{contact.last_seen}}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "ContactItem",
  props: ["contact"]
};
</script>

<style lang="scss" scoped>
.contact__item {
  display: flex;
  justify-content: flex-start;
  align-items: center;
  padding: 15px 20px;
  .contact__item__picture {
    width: 38px;
    height: 38px;
    background: red;
    border-radius: 50%;
    position: relative;
    &::after {
      position: absolute;
      bottom: 0;
      right: 0;
      content: "";
      background: orange;
      width: 10px;
      border: 1px solid white;
      height: 10px;
      border-radius: 50%;
    }

    &.online::after {
      background: green;
    }

    &.offline::after {
      display: none;
    }
    img {
      width: 100%;
      height: 100%;
      border-radius: 50%;
    }
  }

  .contact__item__details {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    margin-left: 10px;
    justify-content: center;
    .contact__item__name {
      font-size: 10pt;
      filter: var(--text-filter);
      transition: 0.3s cubic-bezier(0.4, 0, 0.2, 1) all;
      font-weight: 600;
      letter-spacing: 0.0009px;
    }

    .contact__item__lastseen {
      font-size: 10px;
      filter: var(--text-filter-label);
      color: rgb(41, 54, 82);
      transition: 0.3s cubic-bezier(0.4, 0, 0.2, 1) all;
    }
  }
}
</style>