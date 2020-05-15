
<style lang="scss">
@import url("https://rsms.me/inter/inter.css");
html {
  font-family: "Inter", sans-serif;
}
@supports (font-variation-settings: normal) {
  html {
    font-family: "Inter var", sans-serif;
  }
}
:root {
  --bg-mask: rgba(172, 133, 216, 0.445);
  --sidebar-width: 280px;
  --background-bg-color: rgb(238, 238, 238);
  --post-bg-color: rgb(235, 235, 235);
  --text-filter: none;
  --text-filter-label: none;
  --text-box-filter: none;
  --post-comment-send: 1px solid rgba(0, 0, 0, 0.082);
  --post-box-shadow: 7px 6px 23px #fff7f7 inset;
  --text-body-color: rgba(0, 0, 0, 0.829);

  @media (prefers-color-scheme: dark) {
    --bg-mask: rgba(0, 0, 0, 0.692);
    --background-bg-color: rgb(29, 29, 29);
    --post-bg-color: rgb(36, 36, 36);
    --text-filter: invert(1);
    --text-filter-label: invert(0.85) hue-rotate(180deg);
    --text-body-color: rgb(226, 226, 226);
    --text-box-filter: invert(0.86);
    --post-comment-send: 1px solid rgba(129, 129, 129, 0.384);
    --post-box-shadow: 7px 6px 23px #1313132a inset;
  }
}

* {
  margin: 0;
  padding: 0;
}
body {
  height: auto;

  background: linear-gradient(to bottom, var(--bg-mask), var(--bg-mask)),
    url(./assets/bg2.jpg);

  #main-content {
    background: var(--background-bg-color);
    transition: 0.3s cubic-bezier(0.4, 0, 0.2, 1) all;
    max-width: 80vw;
    height: auto;
    margin: 50px auto;
    margin-top: 50px;
    box-shadow: 0 0 20px rgba(231, 151, 255, 0.123);
    display: grid;
    grid-template-columns: var(--sidebar-width) auto var(--sidebar-width);
  }
}
</style>

<script>
import LeftNavigation from "./components/LeftNavigation";
import CenterContent from "./components/CenterContent";
import RightSidebar from "./components/RightSidebar";
export default {
  components: { LeftNavigation, CenterContent, RightSidebar }
};
</script>

<template>
  <div id="main-content">
    <LeftNavigation />
    <CenterContent />
    <RightSidebar />
  </div>
</template>