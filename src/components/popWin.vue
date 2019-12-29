<template>
  <transition name="fade" >
    <div class="pop-root" v-show="isShowPop">
      <div class="pop-mask" @click="closePop"></div>
      <div class="pop-body">
        <div class="pop-title">
          <div></div>
          <div></div>
        </div>

        <slot name="content"></slot>

        <div class="pop-bottom"></div>
      </div>
    </div>
  </transition>
</template>

<script>
  export default {
    name: 'popWin',

    props: {
      isShowPop: {
        type: Boolean,
        default: false
      }
    },
    data() {
      return {}
    },
    methods: {
      closePop() {
        this.isShowPop = !this.isShowPop
      }
    }
  };
</script>

<style lang="scss" scoped>
  *{
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
      background: rgba(0,0,0,0.3);
      position: absolute;
      height: 100vh;
      width: 100vw;
      z-index: 2001;
    }

    .pop-body {
      width: 80vw;
      min-height: 30vh;
      max-height: 75vh;
      background: #ffffff;
      display: flex;
      z-index: 2100;
    }
  }


</style>
