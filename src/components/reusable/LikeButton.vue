<template>
  <div class="like__container">
    <span class="heart-button" :class="{'active':liked}" @click="hasLiked">
      <span class="material-icons on-active">favorite</span>
      <span class="material-icons not-active">favorite_border</span>

      <span class="circle"></span>
    </span>

    <div class="counter" :class="{'incremented':incremented}">{{likes}}</div>
  </div>
</template>

<script>
export default {
  name: "LikeButton",
  props: ["current_likes"],
  data: function() {
    return {
      liked: false,
      likes: this.current_likes,
      incremented: true
    };
  },
  methods: {
    hasLiked() {
      if (!this.liked) this.likes += 1;
      else this.likes -= 1;
      this.liked = !this.liked;
      this.doIncrement();
    },
    doIncrement() {
      this.incremented = false;
      setTimeout(() => (this.incremented = true), 300);
    }
  }
};
</script>

<style lang="scss" scoped>
$pop-out-color: rgb(225, 210, 250);
$heart-color: rgb(255, 36, 91);

.like__container {
  display: inline-flex;
  justify-content: flex-start;
  align-items: center;
  flex-direction: row;
}

.heart-button {
  color: $heart-color;
  width: 30px;
  height: 30px;
  display: inline-flex;
  justify-content: center;
  align-items: center;
  position: relative;
  user-select: none;

  > span {
    position: absolute;

    &.on-active {
      transform: scale(0);
      opacity: 0;
      transition: 0.2s cubic-bezier(0.53, 0.74, 0.03, 2.13) all;
    }

    &.not-active {
      transition: 0.2s cubic-bezier(0.53, 0.74, 0.03, 2.13) all;
      opacity: 1;
      transition-delay: 0.2s;
    }

    &.circle {
      display: block;
      width: 100%;
      height: 100%;
      border: 0px solid rgb(99, 245, 255);
      border-radius: 100px;
      transform: scale(0);

      // opacity: 0;
    }
  }

  &.active {
    > span.on-active {
      transform: scale(1);
      opacity: 1;
      transition-delay: 0.4s;
    }

    > span.not-active {
      transform: scale(0);

      opacity: 0;
    }

    > span.circle {
      animation: 0.2s pop-out ease-in-out forwards;
      animation-delay: 0.2s;
    }
  }
}

@keyframes pop-out {
  0% {
    border: 30px solid $pop-out-color;
  }
  50% {
    border: 10px solid $pop-out-color;
  }
  70% {
    transform: scale(0.9);
    opacity: 0.6;
    border: 10px solid $pop-out-color;
  }
  100% {
    border: 0px solid $pop-out-color;
    transform: scale(0.8);
    opacity: 0;
  }
}

.counter {
  font-size: 10pt;
  color: #00000060;
  transform: translateY(10px);
  opacity: 0;
  margin: 5px;
  filter: var(--text-filter);
  transition: 0.3s cubic-bezier(0.4, 0, 0.2, 1) filter;
  display: inline-block;
  &.incremented {
    transition: 0.2s cubic-bezier(0.53, 0.74, 0.03, 2.13) all;
    opacity: 1;
    transform: none;
  }
}
</style>