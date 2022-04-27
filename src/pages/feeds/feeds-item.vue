<template>
  <div class="topline">
    <topLine>
      <template #headline>
          <div class="icon-gittogram">
            <iconComponent name="gittogram-icon" />
            </div>
        <div class="headline">
        <div class="icon">
          <iconComponent name="home-icon" />
        </div>
        <div class="icon-avatar">
          <iconComponent name="avatar-icon" />
        </div>
          <div class="icon-exit">
            <iconComponent name="exit-icon" />
            </div>
            </div>
      </template>
      <template #content>
        <ul class="stories">
          <li class="stories-itme" v-for="story in stories" :key="story.id">
            <story-user-item
              :avatar="story.avatar"
              :username="story.username"
              @onPress="handlePress(story.id)"
            />
          </li>
        </ul>
      </template>
    </topLine>

    <template>
      <div class="c-feed">
        <toggler-item />
        <div class="comments" v-if="shown">
          <ul class="comments-list">
            <li class="comments-item" v-for="n in 5" :key="n"></li>
            <comment-item text="Some text" username="Jhoe" />
          </ul>
        </div>
      </div>
    </template>
  </div>
</template>
<script>
import * as api from '@/api'
import StoryUserItem from '@/components/storyUserItem/story-UserItem.vue'
import { topLine } from '@/components/topline'
import { iconComponent } from '@/icons'
import stories from '@/pages/feeds/data.json'
import TogglerItem from '@/components/toggler/toggler-item.vue'
import commentItem from '@/components/comments/comment-item.vue'
export default {
  name: 'feedsItem',
  components: {
    topLine,
    iconComponent,
    StoryUserItem,
    TogglerItem,
    commentItem
  },
  data () {
    return {
      stories
    }
  },
  created () {
    api.trandings.getTrendings()
  }
}
</script>
<style lang= 'scss' scoped src='@/pages/feeds/feeds.scss'>
</style>
