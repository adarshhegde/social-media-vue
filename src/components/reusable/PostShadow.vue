<template>
  <span class="shadow"></span>
</template>

<script>
export default {
  name: "PostShadow"
};
</script>

<style scoped>
.shadow { /* this can be done using a :before or :after pseudoclass as well */
  background: #ff000000;
  position: absolute;
  width: 100%;
  height: 12%;
  bottom: 0px;
  box-shadow: 0 16px 43px #0000000d;
  user-select: none;
  pointer-events: none;
}
</style>