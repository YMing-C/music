<template>
    <div>
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
    </div>
</template>

<script>
import { Swiper, Grid, GridItem } from "vux";
import Mytitle from "../components/MyTitle";

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
    "my-title": Mytitle
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
</style>