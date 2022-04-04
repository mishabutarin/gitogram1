<template>
  <button :class="['button', { acrive: isOpenend }]" @click="toggle">
    <span class="text">
{{ isOpenend ? "Hide": "Show"}} issues
    </span>
    <span class="icon">
      <icon name="triangle"/>
    </span>
  </button>
</template>
<script>
import { icon } from '../../icons'
export default {
  components: {
icon,
  },
  data() {
    return {
      isOpenend: false
    };
  },
  methods: {
    toggle(){
      this.isOpenend = !this.isOpenend;
      this.$emit('onToggle', this.isOpenend)
    }
  },
};
</script>
