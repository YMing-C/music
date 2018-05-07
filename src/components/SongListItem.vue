/**
    插槽:img ， description
    img：图片
    description：文字说明
 */
<template>
    <div>
        <div v-if="hasImgSlot" class="song-list-img-content">
            <slot name="img">
                <img :src="img">
            </slot>
        </div>
        <p v-if="hasDescriptionSlot">
            <slot name="description">
                <span v-html="description"></span>
            </slot>
        </p>
    </div>
</template>

<script>
export default {
  name: "song-list-item",
  props: ["img", "description"],
  mounted() {
    this.$slots.img && (this.hasImgSlot = true);
    this.$slots.description && (this.hasDescriptionSlot = true);
  },
  data() {
    return {
      hasImgSlot: false,
      hasDescriptionSlot: false
    };
  }
};
</script>

<style>
.song-list-img-content {
  width: 100%;
  max-height: 100px;
  overflow: hidden;
}
</style>