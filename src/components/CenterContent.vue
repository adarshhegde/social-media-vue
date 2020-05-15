<template>
  <div class="center__content">
    <h1>Feed</h1>
    <div class="posts__list">
      <div class="post" v-for="post in posts" :key="post.id">
        <ImagePost v-if="(post.type == 'image')" :post="post" />
        <TextPost v-if="(post.type == 'text')" :post="post" />
      </div>
    </div>
  </div>
</template>

<script>
import ImagePost from "./reusable/ImagePost";
import TextPost from "./reusable/TextPost";
export default {
  name: "CenterContent",
  components: {
    ImagePost,
    TextPost
  },
  data: function() {
    return {
      posts: [
        {
          id:"4m3mk",
          type: "text",
          author: "Manoj Sar",
          likes:101,
          postedAt: "50 mins ago.",
          profile_picture:
            "https://i.pinimg.com/originals/36/a8/9b/36a89b3a4628b1504b09060715ec9660.jpg",
          body:
            "Misae and Shin-chan go to see a movie, but Shin-chan bothers her and everyone watching the film. As a result, she is forced to leave. / Yoshinaga asks Shin-chan to keep the surrounding area clean. Everyone gets amazed with Shin-chan's behaviour. / Shin-chan wakes his father for food and acts stubborn with him. He drops the entire juice on the ground."
        },
        {
          id:"mmkmkm2m3km2",
          type: "image",
          author: "Manoj Sar",
          likes:6969,
          postedAt: "1 hour ago.",
          profile_picture:
            "https://i.pinimg.com/originals/36/a8/9b/36a89b3a4628b1504b09060715ec9660.jpg",
            description:"Hehehehehe ",
          body:
            "<img src='https://tv-asahicontents.com/tv-asahi/open/open-tv-program!image?tid=4541&imageNumber=1&sp=true' />"
        },
        {
          id:"mmkmkm2m334km2",
          type: "image",
          author: "Soni Sins",
          postedAt: "2 hour ago.",
          likes:9001,
          profile_picture:
            "https://scontent-maa2-1.xx.fbcdn.net/v/t1.0-9/91837903_2729789473909421_4657730361353043968_o.jpg?_nc_cat=101&_nc_sid=09cbfe&_nc_ohc=6h0bxPrkI6kAX_yxrC8&_nc_ht=scontent-maa2-1.xx&oh=de6c152620e0538749f902557176d6d3&oe=5EE3E890",
            description:"😤👌",
          body:
            "<img src='https://scontent-maa2-1.xx.fbcdn.net/v/t1.0-9/96797823_2767038506851184_4716910578285674496_o.jpg?_nc_cat=100&_nc_sid=825194&_nc_ohc=Vn6PS_CF9OIAX8cwJbH&_nc_ht=scontent-maa2-1.xx&oh=b493e8e93ace2710de8be32bd3f3d987&oe=5EE326C1' />"
        },
      
      ]
    };
  }
};
</script>

<style lang="scss" scoped>
.center__content {
  > h1 {
  font-family: "Balsamiq Sans", cursive;
    color: #353535;
    font-size: 20pt;
    letter-spacing: -0.5004pt;
    font-weight: 100;
    margin: 29px 47px;
    margin-bottom: 20px;
    filter:var(--text-filter);
  }
  > div > div{
    background:var(--post-bg-color);
    box-shadow:var(--post-box-shadow);
    transition:0.3s cubic-bezier(0.4, 0.0, 0.2, 1) all;
  }
}
</style>