<template>
    <div class="footer">
        <flexbox :show-lr-borders="false" :show-vertical-dividers="false" :align="'center'">
            <flexbox-item :span="2" class="song-control-bar-item">
                <div class="song-img-wrap" :class="isPlaying ? 'rotate' : ''">
                    <img :src="img">
                </div>
            </flexbox-item>
            <flexbox-item :span="7" class="song-control-bar-item song-info">
                <div class="song-name">{{songName}}</div>
                <p class="song-lrc">{{songLrc}}</p>
            </flexbox-item>
            <flexbox-item :span="3" class="song-control-bar-item song-control-more">
                <i class="fa" :class="isPlaying ? 'fa-stop-circle-o' : 'fa-play-circle-o'"></i>
                <i class="fa fa-bars"></i>
            </flexbox-item>
        </flexbox>
    </div>
</template>

<script>
import { Flexbox, FlexboxItem } from "vux";

export default {
  name: "comm-footer",
  props: ["img", "songName", "songLrc"],
  components: {
    Flexbox,
    FlexboxItem
  },
  data() {
    return {
      isPlaying: false
    };
  }
};
</script>

<style scoped>
.footer {
  position: fixed;
  left: 0;
  bottom: 0;
  width: 100%;
  height: 50px;
  background-color: #f7f7fa;
}
.footer:before {
  content: " ";
  position: absolute;
  left: 0;
  top: 0;
  right: 0;
  height: 1px;
  border-top: 1px solid #c0bfc4;
  color: #c0bfc4;
  -webkit-transform-origin: 0 0;
  transform-origin: 0 0;
  -webkit-transform: scaleY(0.5);
  transform: scaleY(0.5);
}
.song-control-bar-item {
  padding: 0;
}
.song-control-bar-item::after {
  border: 0;
}
.song-img-wrap {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  overflow: hidden;
  margin: 0 auto;
}
.song-img-wrap img {
  width: 100%;
}
.song-info {
  font-size: 14px;
  line-height: 1.2;
}
.song-control-more {
  height: 50px;
  line-height: 50px;
}
.song-lrc {
  color: #9b9b9b;
}
.fa-play-circle-o,
.fa-stop-circle-o,
.fa-bars {
  font-size: 26px;
  margin-left: 10px;
  color: #35495e;
}
@keyframes rotate {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}
.rotate {
  animation: rotate 10s linear infinite;
}
</style>