<template>
<div class="wrapper">
  <slider class="slider" auto-play="true" show-indicators="true" @change="currentIdx=$event.index">
    <div class="frame" v-for="(img,idx) in imageList" :key="idx">
      <image class="image" resize="contain" :src="img.src"></image>
    </div>
  </slider>
  <div class="indicator">
    <div :class="['i-d',currentIdx==idx?'i-d-act':'']" v-for="(item,idx) in imageList" :key="idx"></div>
  </div>
</div>
</template>

<script>
export default {
  data() {
    return {
      currentIdx: 0,
      imageList: [
        { src: 'https://yanxuan.nosdn.127.net/01de3a547f5448d31f8f45f5a012e1a1.jpg?imageView&quality=75&thumbnail=750x0' },
        { src: 'https://yanxuan.nosdn.127.net/4a08abbe66fbb2969512269ebfdde19f.jpg?imageView&quality=75&thumbnail=750x0' },
        { src: 'https://yanxuan.nosdn.127.net/31044e551b20e851c67b6deea3639430.jpg?imageView&quality=75&thumbnail=750x0' },
        { src: 'https://yanxuan.nosdn.127.net/a2b4bcc5a668b35a2820061022904fa8.jpg?imageView&quality=75&thumbnail=750x0' }
      ]
    }
  },
  methods: {}
}
</script>

<style scoped>
.slider,
.frame,
.image {
    width: 750px;
    height: 370px;
}

.indicator {
    position: absolute;
    left: 0;
    right: 0;
    bottom: 0;
    width: 750px;
    height: 30px;
    flex-direction: row;
    justify-content: center;
}

.i-d {
    width: 30px;
    height: 4px;
    margin-left: 10px;
    background-color: #ffffff;
    opacity: .4;
}

.i-d-act {
    opacity: 1;
}
</style>
