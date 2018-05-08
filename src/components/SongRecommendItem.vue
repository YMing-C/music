<template>
    <div>
        <flexbox>
            <flexbox-item :span="2">
                <div v-if="hasImg">
                    <img class="song-img" :src="img">
                </div>
            </flexbox-item>
            <flexbox-item :span="7">
                <div class="song-name">{{songName}}</div>
                <div class="song-info">{{singer}} · {{album}}</div>
            </flexbox-item>
            <flexbox-item :span="3">1</flexbox-item>
        </flexbox>
    </div>
</template>

<script>
import { Flexbox, FlexboxItem } from "vux";

export default {
  name: "song-recommend-item",
  props: {
    img: {
      required: true
    },
    songName: {
      required: true
    },
    singer: {
      required: true
    },
    album: {
      required: true
    }
  },
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
.song-img {
  max-width: 100%;
  height: 58px;
}
.song-name {
  color: #000;
  font-size: 14px;
}
.song-info {
  color: grey;
  font-size: 12px;
}
</style>

