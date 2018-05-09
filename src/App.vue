<template>
    <div id="app">
        <comm-header></comm-header>
        <router-view></router-view>
        <comm-footer></comm-footer>
    </div>
</template>

<script>
import commHeader from "./components/CommHeader";
import commFooter from "./components/CommFooter";
export default {
  name: "app",
  components: {
    "comm-header": commHeader,
    "comm-footer": commFooter
  }
};
</script>

<style lang="less">
@import "~vux/src/styles/reset.less";

body {
  background-color: #fbf9fe;
}
</style>
