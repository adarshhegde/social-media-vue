<template>
  <div class="post__commentbox">
    <input type="text" placeholder="Write a comment." />
    <button>
      <i class="far fa-paper-plane"></i>
    </button>
  </div>
</template>

<script>
export default {
  name: "CommentBox"
};
</script>

<style lang="scss" scoped>
.post__commentbox {
  display: flex;
  justify-content: space-between;

  width: 95%;
  margin: auto;
  input[type="text"] {
    padding: 10px;
    border: 1px solid #0000002e;
    font-family: "Inter var", sans-serif;
    width: 95%;
    filter: var(--text-box-filter);
    transition: 0.3s cubic-bezier(0.4, 0, 0.2, 1) filter;
  }

  button {
    width: 42px;
    border: var(--post-comment-send);
    transition: 0.3s cubic-bezier(0.4, 0, 0.2, 1) all;
    margin-left: 5px;
    color: #27ace0;
    line-height: 0;

    background: transparent;
  }
}
</style>