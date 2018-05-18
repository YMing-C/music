/**
    props: show;
    show: 控制显示/隐藏
 */
<template>
    <div class="playing-list">
        <div class="playing-list-song-list-content" :class="isShow ? 'playing-list-song-list-content_toggle' : '' ">
            <div class="playing-list-bar">
                单曲循环
                <div class="right-function-bar">
                    <i class="fa fa-download"></i>
                    <i class="fa fa-plus-square-o"></i>
                    <i class="fa fa-trash-o"></i>
                </div>
            </div>

            <ul class="playing-list-song-list">
                <li class="playing-list-song-list-item">
                    说散就散
                    <span class="playing-list-song-list-item-singer">- 袁娅维</span>
                    <div class="playing-list-song-list-item-function-bar">
                        <i class="fa fa-heart-o"></i>
                        <i class="vux-close"></i>
                    </div>
                </li>
                <li class="playing-list-song-list-item">
                    说散就散
                    <span class="playing-list-song-list-item-singer">- 袁娅维</span>
                    <div class="playing-list-song-list-item-function-bar">
                        <i class="fa fa-heart-o"></i>
                        <i class="vux-close"></i>
                    </div>
                </li>
                <li class="playing-list-song-list-item">
                    说散就散
                    <span class="playing-list-song-list-item-singer">- 袁娅维</span>
                    <div class="playing-list-song-list-item-function-bar">
                        <i class="fa fa-heart-o"></i>
                        <i class="vux-close"></i>
                    </div>
                </li>
                <li class="playing-list-song-list-item">
                    说散就散
                    <span class="playing-list-song-list-item-singer">- 袁娅维</span>
                    <div class="playing-list-song-list-item-function-bar">
                        <i class="fa fa-heart-o"></i>
                        <i class="vux-close"></i>
                    </div>
                </li>
                <li class="playing-list-song-list-item">
                    说散就散
                    <span class="playing-list-song-list-item-singer">- 袁娅维</span>
                    <div class="playing-list-song-list-item-function-bar">
                        <i class="fa fa-heart-o"></i>
                        <i class="vux-close"></i>
                    </div>
                </li>
                <li class="playing-list-song-list-item">
                    说散就散
                    <span class="playing-list-song-list-item-singer">- 袁娅维</span>
                    <div class="playing-list-song-list-item-function-bar">
                        <i class="fa fa-heart-o"></i>
                        <i class="vux-close"></i>
                    </div>
                </li>
                <li class="playing-list-song-list-item">
                    说散就散
                    <span class="playing-list-song-list-item-singer">- 袁娅维</span>
                    <div class="playing-list-song-list-item-function-bar">
                        <i class="fa fa-heart-o"></i>
                        <i class="vux-close"></i>
                    </div>
                </li>
                <li class="playing-list-song-list-item">
                    说散就散
                    <span class="playing-list-song-list-item-singer">- 袁娅维</span>
                    <div class="playing-list-song-list-item-function-bar">
                        <i class="fa fa-heart-o"></i>
                        <i class="vux-close"></i>
                    </div>
                </li>
                <li class="playing-list-song-list-item">
                    说散就散
                    <span class="playing-list-song-list-item-singer">- 袁娅维</span>
                    <div class="playing-list-song-list-item-function-bar">
                        <i class="fa fa-heart-o"></i>
                        <i class="vux-close"></i>
                    </div>
                </li>
                <li class="playing-list-song-list-item">
                    说散就散
                    <span class="playing-list-song-list-item-singer">- 袁娅维</span>
                    <div class="playing-list-song-list-item-function-bar">
                        <i class="fa fa-heart-o"></i>
                        <i class="vux-close"></i>
                    </div>
                </li>
            </ul>

            <div class="playing-list-close-bar" @click="isShow=!isShow">
                关 闭
            </div>
        </div>
        <div class="playing-list-mask" :class="isShow? '' : 'playing-list-mask_toggle'" @click="isShow=!isShow"></div>
    </div>
</template>

<script>
export default {
  name: "playing-list",
  props: ["show"],
  watch: {
    show: function() {
      this.isShow = true;
    }
  },
  data() {
    return {
      isShow: false
    };
  }
};
</script>

<style scoped>
.playing-list {
  max-height: 50%;
}
.playing-list-mask {
  position: fixed;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
  background: rgba(0, 0, 0, 0.6);
  z-index: 1000;
}
.playing-list-mask_toggle {
  display: none;
}
.playing-list-song-list-content {
  position: fixed;
  left: 0;
  bottom: 0;
  width: 100%;
  z-index: 5000;
  max-height: 80%;
  background: #fff;
  -webkit-transform: translate(0, 100%);
  transform: translate(0, 100%);
  -webkit-backface-visibility: hidden;
  backface-visibility: hidden;
  -webkit-transition: -webkit-transform 0.3s;
  transition: -webkit-transform 0.3s;
  transition: transform 0.3s;
  transition: transform 0.3s, -webkit-transform 0.3s;
}
.playing-list-song-list-content_toggle {
  -webkit-transform: translate(0, 0%);
  transform: translate(0, 0%);
}
.playing-list-bar {
  color: #999;
  padding: 10px 8px;
  font-size: 14px;
  height: 28px;
  line-height: 28px;
  position: relative;
}
.playing-list-bar:after {
  content: " ";
  position: absolute;
  height: 1px;
  left: 0;
  right: 0;
  bottom: 0;
  background: #d9d9d9;
  -webkit-transform: scaleY(0.5);
  transform: scaleY(0.5);
}
.right-function-bar {
  float: right;
  line-height: 1;
}
.right-function-bar .fa {
  font-size: 22px;
  padding: 5px 10px;
}
.playing-list-song-list {
  position: relative;
  height: 300px;
  overflow: scroll;
}
.playing-list-close-bar {
  position: relative;
}
.playing-list-close-bar:before {
  position: absolute;
  content: "";
  left: 0;
  right: 0;
  top: 0;
  height: 1px;
  background: #d9d9d9;
  -webkit-transform: scaleY(0.5);
  transform: scaleY(0.5);
}
.playing-list-song-list .playing-list-song-list-item {
  position: relative;
  padding: 10px 0 10px 15px;
  height: 28px;
  line-height: 28px;
}
.playing-list-song-list .playing-list-song-list-item:after {
  position: absolute;
  content: "";
  left: 15px;
  right: 0;
  bottom: 0;
  height: 1px;
  background: #d9d9d9;
  -webkit-transform: scaleY(0.5);
  transform: scaleY(0.5);
}
.playing-list-song-list .playing-list-song-list-item:last-child::after {
  height: 0;
}
.playing-list-song-list-item-singer {
  color: #999;
  font-size: 14px;
}
.playing-list-song-list-item-function-bar {
  float: right;
  margin-right: 10px;
}
.playing-list-song-list-item-function-bar .fa {
  font-size: 20px;
  color: #999;
  margin-right: 10px;
}
.playing-list-song-list-item-function-bar .vux-close {
  width: 20px;
  height: 20px;
}
.playing-list-song-list-item-function-bar .vux-close::before,
.playing-list-song-list-item-function-bar .vux-close::after {
  top: 7px;
}
.playing-list-close-bar {
  padding: 10px 0;
  text-align: center;
  font-size: 15px;
}
</style>

