<template>
    <div id="app">
        <comm-header></comm-header>
        <router-view></router-view>
    </div>
</template>

<script>
import commHeader from "./components/CommHeader";
export default {
  name: "app",
  components: {
    "comm-header": commHeader
  }
};
</script>

<style lang="less">
@import "~vux/src/styles/reset.less";

body {
  background-color: #fbf9fe;
}
</style>
