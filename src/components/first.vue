<template>
  <div style="position: absolute">
    <div style="float:left;height: 684px;width: 684px;background-color: rgb(234, 235, 239);  border-radius: 2em;">
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
    <div style="float:left;height: 335px;width: 330px;margin-left: 14px;margin-top: 14px;background-color: #E6E6E6;  border-radius: 2em;
">
      <img :src="imgs[4].path" class="imgnormal" @mouseover="bigger" @mouseleave="normal">
    </div>
  </div>
</template>

<script>
export default {
  name: 'first',
  data: function () {
    return {
      imgs: [
        { path: require('../assets/first/img.png') },
        { path: require('../assets/first/img_1.png') },
        { path: require('../assets/first/img_2.png') },
        { path: require('../assets/first/img_3.png') },
        { path: require('../assets/first/img_4.png') }

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
  border-radius: 2em;
  height: 100%;
  width: 100%
}

.head {
  border-radius: 2em;
  padding-right: 34px;
  height: 650px;
  width: 650px
}
</style>
