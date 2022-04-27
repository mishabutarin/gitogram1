<template>
  <button class="c-story-user-item" @click="$emit('onPress')">
<div class="avatar">
  <img :src="avatar" alt="" class="img__ava"/>
</div>
<div class="username">{{username}}</div>
  </button>
  <slider-user-story ref="modal" :showStories='showStories' @close='closeModal()'></slider-user-story>
</template>
<script>
import { SliderUserStory } from '@/components/sliderUserStory/sliderUserStory.vue'
export default {
  name: 'StoryUserItem',
  template: 'StoryUserItem',
  components: {
    SliderUserStory
  },
  props: {
    avatar: {
      type: String,
      required: true
    },
    username: {
      type: String,
      required: true
    }
  }
}
</script>
<style lang="scss" scoped src='./storyUserItem.scss'></style>
