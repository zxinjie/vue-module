<template>
  <transition name="fade">
    <div class="pop-root">
      <div class="pop-mask" @click="closePop"></div>
      <div class="pop-body">
        <div class="pop-title">
          <div>关闭</div>
        </div>

        <div class="pop-content">
          <slot name="content"></slot>
        </div>
        <div class="pop-bottom"></div>
      </div>
    </div>
  </transition>
</template>

<script>
export default {
  name: "popWin",

  props: {},
  data() {
    return {};
  },
  methods: {
    closePop() {
      this.isShowPop = !this.isShowPop;
    }
  },
  computed: {
    reverseShowState() {}
  },
  mounted() {
    console.log(this.isShowPop);
  }
};
</script>

<style lang="scss" scoped>
* {
  margin: 0;
  padding: 0;
}

.pop-root {
  width: 100%;
  height: 100%;
  display: flex;
  position: absolute;
  top: 0;
  left: 0;
  justify-content: center;
  align-items: center;
  z-index: 2000;
  
  .pop-mask {
    background: rgba(2, 2, 2, 0.3);
    position: absolute;
    height: 100vh;
    width: 100vw;
    z-index: 2001;
  }

  .pop-body {
    width: 80vw;
    max-height: 80vh;
    background: #ffffff;
    z-index: 2100;
    display: flex;
    flex-direction: column;
    border-radius: 15px;

    .pop-title {
      height: 31px;
      background: green;
      text-align: right;
    }

    .pop-content {
      display: flex;
      background: gray;
    }
  }
}
</style>
