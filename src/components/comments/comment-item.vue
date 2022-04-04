<template>
  <div class="c-comment">
    <p>
      <span class="username">{{ username }}</span>
    </p>
  </div>
</template>
<script>
export default {
  name: 'Comment',
  props: {
    username: {
      type: String,
      required: true
    },
    Text: {
      type: String,
      required: true
    }
  }
}
</script>
