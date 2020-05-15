<template>
  <div class="post_image">
    <PostShadow />
    <div class="post__header">
      <img :src="post.profile_picture" />
      <div>
        <span class="post__author">{{post.author}}</span>
        <span class="post__time">{{post.postedAt}}</span>
      </div>
    </div>

    <div class="post__content">
      <p class="post__description">{{post.description}}</p>
      <div class="post__body" v-html="post.body"></div>
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
  name: "ImagePost",
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
.post_image {
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
      filter: var(--text-filter);
      transition: 0.3s cubic-bezier(0.4, 0, 0.2, 1) all;

      display: flex;
      flex-direction: column;
      justify-content: center;
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
    .post__description {
      line-height: 24px;
      font-size: 14px;
      padding: 25px;
      color: var(--text-body-color);
      transition: 0.3s cubic-bezier(0.4, 0, 0.2, 1) all;
    }
    .post__body {
      display: flex;
      justify-content: center;

      /deep/ img {
        background: #13131333;
        width: 94%;
        border-radius: 10px;
      }
    }
  }

  .post__interactions {
    margin: auto 24px;
    margin-bottom: 10px;
    margin-top: 15px;
    display: flex;
    align-items: center;
  }
}
</style>