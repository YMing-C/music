<template>
    <div id="app" style="height:100%;">
        <drawer width="80%" :show.sync="drawerVisibility" :show-mode="showModeValue" :placement="showPlacementValue" :drawer-style="{'background-color':'#35495e', width: '80%'}">

            <!-- drawer content -->
            <div slot="drawer">
                <group title="功能区" style="margin-top:20px;">
                    <cell title="升级VIP" value="畅想音乐特权" @click.native="drawerVisibility = false">
                    </cell>
                    <cell title="个性装扮" @click.native="drawerVisibility = false">
                    </cell>
                    <cell title="消息中心" @click.native="drawerVisibility = false">
                    </cell>
                </group>
            </div>

            <view-box>
                <comm-header @show="showDrawer"></comm-header>
                <router-view></router-view>
                <comm-footer :img="require('./assets/images/squre1.jpg')" :songName="'体面'" :songLrc="'于文文'"></comm-footer>
            </view-box>
        </drawer>
    </div>
</template>

<script>
import commHeader from "./components/CommHeader";
import commFooter from "./components/CommFooter";
import { Drawer, Group, Cell, ViewBox } from "vux";
export default {
  name: "app",
  components: {
    Drawer,
    Group,
    Cell,
    ViewBox,
    "comm-header": commHeader,
    "comm-footer": commFooter
  },
  data() {
    return {
      drawerVisibility: false,
      showMode: "push",
      showModeValue: "push",
      showPlacement: "left",
      showPlacementValue: "left"
    };
  },
  methods: {
    showDrawer: function() {
      this.drawerVisibility = true;
    }
  }
};
</script>

<style lang="less">
@import "~vux/src/styles/reset.less";

body,
html {
  height: 100%;
  width: 100%;
  overflow-x: hidden;
}

body {
  background-color: #fbf9fe;
}
</style>
