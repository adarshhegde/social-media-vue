<template>
  <nav>
    <a
      v-for="menu in menus"
      :key="menu.title"
      class="navigation__item"
      :class='{"active": (menu.text == active)}'
    >
      <i class="fas" :class="menu.icon"></i>
      <span>{{menu.text}}</span>
    </a>
  </nav>
</template>

<script>
export default {
  name: "Navigation",
  props: ["menus", "active"]
};
</script>

<style scoped lang="scss">
nav {
  display: flex;
  flex-direction: column;
  width: 90%;

  position: sticky;
  top: 35px;
  left: 0;

  .navigation__item {
    padding: 5px 10px;
    // border:1px solid black;
    color: #74278b63;

    display: flex;
    font-weight: 500;
    font-size: 10pt;
    justify-content: flex-start;
    align-items: center;
    i {
      width: 52px;
      height: 32px;
      // background:red;
      display: flex;
      justify-content: center;
      align-items: center;
      font-size: 12pt;
      &.smaller {
        font-size: 11pt;
      }
    }

    &.active {
      color: rgb(36, 134, 199);
      font-weight: 600;
      background: #0099ff29;
      border-radius: 27px;
    }
  }
}
</style>