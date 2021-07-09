<template>
  <div style="position: absolute">
    <div style="float:left;height: 684px;width: 684px;background-color: rgb(230, 230, 230);  border-radius: 2em;">
      <img :src="imgs[0].path" class="head" @mouseover="hbigger" @mouseleave="hnormal">
    </div>
    <div
      style="float:left;height: 335px;width: 330px;margin-left: 14px;margin-top: 0px;background-color: #E6E6E6;  border-radius: 2em;
">
      <img :src="imgs[1].path" class="imgnormal" @mouseover="bigger" @mouseleave="normal">
    </div>
    <div
      style="float:left;height: 335px;width: 330px;margin-left: 14px;margin-top: 0px;background-color: #E6E6E6;  border-radius: 2em;
">
      <img :src="imgs[2].path" class="imgnormal" @mouseover="bigger" @mouseleave="normal">
    </div>
    <div
      style="float:left;height: 335px;width: 330px;margin-left: 14px;margin-top: 14px;background-color: #E6E6E6;  border-radius: 2em;
">
      <img :src="imgs[3].path" class="imgnormal" @mouseover="bigger" @mouseleave="normal">
    </div>
    <div style="float:left;height: 335px;width: 330px;margin-left: 14px;margin-top: 14px;background-color: #E6E6E6;  border-radius: 2em;">
      <img :src="imgs[4].path" class="imgnormal" @mouseover="bigger" @mouseleave="normal">
    </div>
  </div>
</template>

<script>
export default {
  name: 'third',
  data: function () {
    return {
      imgs: [
        { path: require('../assets/third/img.png') },
        { path: require('../assets/third/img_1.png') },
        { path: require('../assets/third/img_2.png') },
        { path: require('../assets/third/img_3.png') },
        { path: require('../assets/third/img_4.png') }

      ]
    }
  },
  methods: {
    bigger: function (e) {
      e.target.className = 'imgtouch'
    },
    normal: function (e) {
      e.target.className = 'imgnormal'
    },
    hbigger: function (e) {
      e.target.className = 'headtouch'
    },
    hnormal: function (e) {
      e.target.className = 'head'
    }
  }
}
</script>
<style scoped>
.test {
  border: 2px solid red;
}

.imgtouch {
  height: 168px;
  width: 168px;
  margin-top: 40px;
}

.imgnormal {
  height: 160px;
  width: 160px;
  margin-top: 40px;
}

.headtouch {
  margin-left: 5px;
  margin-top: 115px;
  border-radius: 2em;
  height: 395px;
  width: 395px
}

.head {
  margin-left: 5px;
  margin-top: 115px;
  border-radius: 2em;
  /*padding-right: 34px;*/
  height: 376px;
  width: 376px
}
</style>
