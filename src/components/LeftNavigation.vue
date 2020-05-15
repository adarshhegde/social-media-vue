<template>
  <div class="left__navigation">
      <ProfileSmall/>
      <Navigation :menus="menus" :active="currentlyActive"/>
  </div>
</template>

<script>
import Navigation from './reusable/Navigation';
import ProfileSmall from './reusable/ProfileSmall';
export default {
  name: "LeftNavigation",
  components:{
      Navigation,
      ProfileSmall
  },
  data() {
    return {
      menus: [
        { icon: "fa-home",  text: "Home" },

        { icon: "fa-bell", text: "Notificatons" },

        { icon: "fa-user", text: "Profile" },

        { icon: "fa-ellipsis-v smaller", text: "More" }
      ],
      currentlyActive:"Home"
    };
  }
};
</script>

<style lang="scss" scoped>
.left__navigation {
    //   border-right: 1px solid #71717133;
  width:100%;
  height:100%;
  display:flex;
  flex-direction:column;
  justify-content: flex-start;
  align-items:center;
}
</style>