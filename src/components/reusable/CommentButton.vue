<template>
  <span class="post_comments">
    <i class="far fa-comments"></i>
    <span class="post__comments_no">52 Comments</span>
  </span>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.post_comments {
  font-size: 10pt;
  color: #00000060;

  height: 30px;
  display: inline-flex;
  justify-content: center;
  align-items: center;
  > i {
    margin: auto 15px;
    margin-right: 10px;
    font-size: 15pt;
    color: rgb(39, 172, 224);
  }

  .post__comments_no {
    filter: var(--text-filter);
    transition: 0.3s cubic-bezier(0.4, 0, 0.2, 1) all;
  }
}
</style>