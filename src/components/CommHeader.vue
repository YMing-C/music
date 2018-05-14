<template>
    <div>
        <x-header>
            <i slot="overwrite-left" class="fa fa-bars" @click="show"></i>
            <grid slot="overwrite-title" class="my-title-content">
                <grid-item link="/music" class="my-title-item">我的</grid-item>
                <grid-item link="/" class="my-title-item active">音乐馆</grid-item>
                <grid-item link="/discovery" class="my-title-item">发现</grid-item>
            </grid>
            <i slot="right" class="fa fa-plus"></i>
        </x-header>
        <search placeholder="给你推荐一首，纸短情长" :auto-fixed="false"></search>
    </div>
</template>


<script>
import { XHeader, Grid, GridItem, Search } from "vux";

export default {
  components: {
    XHeader,
    Grid,
    GridItem,
    Search
  },
  methods: {
    show: function() {
      this.$emit("show");
    }
  }
};
</script>

<style scoped>
.my-title-item {
  padding-top: 0 !important;
  padding-bottom: 0 !important;
  height: 42px;
  line-height: 42px;
  text-align: center;
  color: #fff;
}
.my-title-content:before,
.my-title-content::after,
.my-title-item::after,
.my-title-item::before {
  border: 0 !important;
}
.my-title-item:active {
  background: inherit !important;
}
.my-title-item.active {
  font-weight: bold !important;
}
.fa-plus,
.fa-bars {
  font-size: 23px;
}
</style>