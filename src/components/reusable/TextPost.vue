<template>
  <div class="post__text">
    <PostShadow />
    <div class="post__header">
      <img :src="post.profile_picture" />
      <div>
        <span class="post__author">{{post.author}}</span>
        <span class="post__time">{{post.postedAt}}</span>
      </div>
    </div>

    <div class="post__content">
      <div class="post__body" v-html="post.body">{{post.description}}</div>
    </div>

    <div class="post__interactions">
      <LikeButton :current_likes="post.likes" />
      <CommentButton />
    </div>
    <CommentBox />
  </div>
</template>

<script>
import LikeButton from "./LikeButton";
import CommentButton from "./CommentButton";
import CommentBox from "./CommentBox";
import PostShadow from "./PostShadow";
export default {
  name: "TextPost",
  components: {
    LikeButton,
    CommentButton,
    CommentBox,
    PostShadow
  },
  props: ["post"]
};
</script>

<style lang="scss" scoped>
.post__text {
  margin: 28px;
  /* border-radius: 5px; */
  padding-bottom: 22px;
  position: relative;
  .post__header {
    max-width: inherit;
    display: flex;
    justify-content: flex-start;
    align-items: center;
    height: 28px;
    margin: auto 18px;
    padding-top: 24px;

    img {
      height: 40px;
      width: 40px;
      border-radius: 50%;
    }
    > div {
      display: flex;
      flex-direction: column;
      justify-content: center;
      filter: var(--text-filter);
      transition: 0.3s cubic-bezier(0.4, 0, 0.2, 1) all;
      align-items: flex-start;
      margin-left: 10px;
      span.post__author {
        font-size: 16px;
        line-height: 28px;
      }

      span.post__time {
        font-size: 11px;
        line-height: 20px;
      }
    }
  }
  .post__content {
    .post__body {
      line-height: 24px;
      font-size: 14px;
      padding: 25px;
      color: var(--text-body-color);
      transition: 0.3s cubic-bezier(0.4, 0, 0.2, 1) all;
    }
  }

  .post__interactions {
    margin: auto 24px;
    margin-bottom: 10px;
    display: flex;
    align-items: center;
  }
}
</style>