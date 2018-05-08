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
            <div class="icon-content">
                <i class="fa fa-headphones"></i>
                <span class="collection-frequency" v-if="hasFrequency">{{frequency}}万</span>
                <i class="fa fa-play-circle-o"></i>
            </div>
        </div>
        <p v-if="hasDescriptionSlot" class="song-list-description">
            <slot name="description">
                <span v-html="description"></span>
            </slot>
        </p>
    </div>
</template>

<script>
export default {
  name: "song-list-item",
  props: ["img", "description", "frequency"],
  mounted() {
    this.$props.frequency && (this.hasFrequency = true);
    this.$slots.img && (this.hasImgSlot = true);
    this.$slots.description && (this.hasDescriptionSlot = true);
  },
  data() {
    return {
      hasFrequency: false,
      hasImgSlot: false,
      hasDescriptionSlot: false
    };
  }
};
</script>

<style scoped>
.song-list-img-content {
  position: relative;
  width: 100%;
  max-height: 110px;
  overflow: hidden;
}
.song-list-description {
  font-size: 12px;
  padding: 2px;
  color: #1b1818;
}
.icon-content {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  padding: 0 4px;
  box-sizing: border-box;
}
.fa-play-circle-o,
.fa-headphones {
  color: #fff;
  font-size: 12px;
}
.fa-play-circle-o {
  float: right;
  font-size: 18px;
  margin-top: 4px;
}
.collection-frequency {
  color: #ffffff;
  font-size: 11px;
}
</style>