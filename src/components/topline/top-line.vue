<template>
<div class="c-topline">
  <div class="container">
    <div class="headline">
      <slot name= "headline" />
    </div>
    <div class="content">
      <slot name= "content" v-if ="$slots.content"/>
    </div>
  </div>
</div>
</template>
<style lang= "scss" src= './topline.scss' scoped>

</style>
