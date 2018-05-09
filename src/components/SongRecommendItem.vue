<template>
    <div>
        <flexbox class="list-content">
            <flexbox-item :span="2">
                <div v-if="hasImg">
                    <img class="song-img" :src="img">
                </div>
            </flexbox-item>
            <flexbox-item :span="9" class="list-item-song-info">
                <div class="song-name">{{songName}}</div>
                <div class="song-info">{{singer}} · {{album}}</div>
            </flexbox-item>
            <flexbox-item :span="1">
                <i class="fa fa-ellipsis-h"></i>
            </flexbox-item>
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
.list-content {
  line-height: 1;
}
.list-item-song-info {
  line-height: 1.5;
}
.song-img {
  width: 100%;
}
.song-name {
  color: #000;
  font-size: 14px;
}
.song-info {
  color: grey;
  font-size: 12px;
}
.fa-ellipsis-h {
  color: #9b9b9b;
}
</style>

