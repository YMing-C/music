<template>
    <div style="padding-bottom:50px;">
        <swiper :list="imgList" auto style="width:100%;margin:0 auto;" height="180px" dots-position="right"></swiper>
        <grid :cols="3" :show-lr-borders="false" :show-vertical-dividers="false">
            <grid-item class="fun-grid-item">
                <i class="fa fa-music"></i>歌手
            </grid-item>
            <grid-item class="fun-grid-item">
                <i class="fa fa-paw"></i>排行榜
            </grid-item>
            <grid-item class="fun-grid-item">
                <i class="fa fa-podcast"></i>电台
            </grid-item>
            <grid-item class="fun-grid-item">
                <i class="fa fa-map-signs"></i>分类歌单
            </grid-item>
            <grid-item class="fun-grid-item">
                <i class="fa fa-video-camera"></i>视频MV
            </grid-item>
            <grid-item class="fun-grid-item">
                <i class="fa fa-circle-o"></i>数字专辑
            </grid-item>
        </grid>
        <my-title title="歌 单 推 荐"></my-title>
        <grid class="song-list-item-wrap" :cols="3" :show-lr-borders="false" :show-vertical-dividers="false">
            <grid-item class="song-list-item-content" v-for="i in 6" :key="i">
                <song-list-item :frequency="42.2">
                    <img slot="img" src="../assets/images/squre.jpg" alt="">
                    <span slot="description">经典老歌，昨日重现 | 感觉走过好多年</span>
                </song-list-item>
            </grid-item>
        </grid>
        <my-title title="每 日 歌 曲 推 荐"></my-title>
        <grid :cols="1" class="song-recommend-item-wrap">
            <grid-item class="song-recommend-item-content" v-for="i in 5" :key="i">
                <song-recommend-item :img="require('../assets/images/squre.jpg')" :songName="'纸短情长'" :singer="'烟把儿乐队'" :album="'不知道'"></song-recommend-item>
            </grid-item>
        </grid>
        <my-title title="新 歌 速 递"></my-title>
        <grid class="song-list-item-wrap" :cols="3" :show-lr-borders="false" :show-vertical-dividers="false">
            <grid-item class="song-list-item-content" v-for="i in 3" :key="i">
                <song-list-item>
                    <img slot="img" src="../assets/images/squre.jpg" alt="">
                    <span slot="description">后来的我们 - 五月天</span>
                </song-list-item>
            </grid-item>
        </grid>
    </div>
</template>

<script>
import { Swiper, Grid, GridItem } from "vux";
import Mytitle from "../components/MyTitle";
import SongListItem from "../components/SongListItem";
import SongRecommendItem from "../components/SongRecommendItem";

const imgList = [
  {
    url: "javascript:;",
    img: require("../assets/images/1.jpg"),
    title: ""
  },
  {
    url: "javascript:;",
    img: require("../assets/images/2.jpg"),
    title: ""
  },
  {
    url: "javascript:;",
    img: require("../assets/images/3.jpg"),
    title: ""
  }
];

export default {
  components: {
    Swiper,
    Grid,
    GridItem,
    "my-title": Mytitle,
    "song-list-item": SongListItem,
    "song-recommend-item": SongRecommendItem
  },
  data() {
    return {
      imgList: imgList
    };
  }
};
</script>

<style scoped>
.fa-circle-o,
.fa-map-signs,
.fa-video-camera,
.fa-podcast,
.fa-paw,
.fa-music {
  font-size: 22px;
  color: #09bb07;
  padding-right: 5px;
  padding-left: 8px;
}

.fun-grid-item {
  color: rgb(47, 46, 46);
}
.fun-grid-item::after {
  border: 0 !important;
}
.song-recommend-item-wrap::before,
.song-list-item-wrap::before {
  border-top: 0;
}
.song-recommend-item-content::after {
  border: 0;
}
.song-recommend-item-content,
.song-list-item-content {
  padding: 5px 2px;
}
.song-list-item-content:nth-child(1),
.song-list-item-content:nth-child(4n) {
  padding-left: 0px;
  padding-right: 2px;
}
.song-list-item-content:nth-child(3n) {
  padding-right: 0px;
  padding-left: 2px;
}
.song-list-item-content:nth-child(3n-1) {
  padding: 5px 1px;
}
.song-list-item-content::after {
  border-bottom: 0;
}
.song-recommend-item-content {
  padding-left: 0;
}
</style>