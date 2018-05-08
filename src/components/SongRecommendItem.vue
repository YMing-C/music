<template>
    <div>
        <flexbox>
            <flexbox-item :span="3">
                <div v-if="hasImg">
                    <img :src="img">
                </div>
            </flexbox-item>
            <flexbox-item :span="6">2</flexbox-item>
            <flexbox-item :span="3">1</flexbox-item>
        </flexbox>
    </div>
</template>

<script>
import { Flexbox, FlexboxItem } from "vux";

export default {
  name: "song-recommend-item",
  props: ["img"],
  components: {
    Flexbox,
    FlexboxItem
  },
  mounted() {
    this.$props.img && (this.hasImg = true);
  },
  data() {
    return {
      hasImg: false
    };
  }
};
</script>

<style scoped>

</style>

