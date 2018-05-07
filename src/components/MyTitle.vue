/**
    传参：title
    title:标题文字
 */
<template>
    <div class="my-title">
        {{title}}
        <i class="fa fa-chevron-circle-right"></i>
    </div>
</template>

<script>
export default {
  name: "my-title",
  props: ["title"]
};
</script>

<style>
.my-title {
  text-align: center;
  position: relative;
}
.my-title .fa {
  position: absolute;
  top: 2px;
  right: 15px;
  font-size: 21px;
  color: gray;
}
</style>
