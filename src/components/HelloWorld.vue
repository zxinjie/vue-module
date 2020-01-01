<template>
  <div>
    <div @click="startPop">点击弹框</div>
    <pop-win v-model="isShowPop">
      <content-view slot="content"></content-view>
    </pop-win>

    <vui-swiper
      height="171px"
      :options="swiperOption"
      :imageList="bannerList"
      effect="zoom"
      @onClick="handleSwiperClick"
    ></vui-swiper>
  </div>
</template>

<script>
import vuiSwiper from "./vui-swiper";
import PopWin from "./popWin";
import contentView from "./contentView";
export default {
  name: "HelloWorld",
  components: {
    PopWin,
    vuiSwiper,
    contentView
  },
  data() {
    return {
      bannerList: [
        {
          img: 'https://ss1.bdstatic.com/70cFuXSh_Q1YnxGkpoWK1HF6hhy/it/u=1480623082,1028728801&fm=26&gp=0.jpg'
        },
        {
          img: "https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=1062896970,1967996506&fm=26&gp=0.jpg"
        },
        {
          img: "https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=1088079182,2468727128&fm=26&gp=0.jpg"
        }
      ],
      swiperOption: {
        showDots: true, // 是否显示分页器
        interval: 3000, // 轮播间隔时间，默认3s
        autoplay: true, // 是否自动播放
        loop: false // 是否循环轮播
      },
      isShowPop: false,
    };
  },
  methods: {
    handleSwiperClick() {

    },
    startPop() {
        this.isShowPop = !this.isShowPop
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
