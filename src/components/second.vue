<template>
  <div>
    <div style="position: absolute;height: 680px;width: 340px;padding-left: 4px">
      <div style="float: top;height: 331px;width: 331px;margin-top: 2px;background-color: #E6E6E6;  border-radius: 2em;
">
        <img :src="imgs[0].path" class="imgnormal" @mouseover="bigger" @mouseleave="normal">
      </div>
      <div style="float: top;height: 331px;width: 331px;margin-top: 2px;background-color: #E6E6E6;  border-radius: 2em;
">
        <img :src="imgs[1].path" class="imgnormal" @mouseover="bigger" @mouseleave="normal">
      </div>
    </div>
    <div
      style="position: absolute;height: 680px;width: 1020px;padding-left: 4px;margin: 0px 0px 0px 360px">
      <div style="float: left;height: 668px;width: 665px;margin-top: 2px;background-color: #E6E6E6;  border-radius: 2em;
">
        <img :src="imgs[2].path" class="head" @mouseover="hbigger" @mouseleave="hnormal">
      </div>
      <div style="float: left;height: 331px;width: 331px;margin: 2px 0px 0px 13px;background-color: #E6E6E6;  border-radius: 2em;
">
        <img :src="imgs[3].path" class="imgnormal" @mouseover="bigger" @mouseleave="normal">
      </div>
      <div style="float: left;height: 331px;width: 331px;margin: 2px 0px 0px 13px;background-color: #E6E6E6;  border-radius: 2em;
">
        <img :src="imgs[4].path" class="imgnormal" @mouseover="bigger" @mouseleave="normal">
      </div>
    </div>
  </div>

</template>

<script>
export default {
  name: 'second',
  data: function () {
    return {
      imgs: [
        { path: require('../assets/second/img.png') },
        { path: require('../assets/second/img_1.png') },
        { path: require('../assets/second/img_2.png') },
        { path: require('../assets/second/img_3.png') },
        { path: require('../assets/second/img_4.png') }

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
  border: 2px solid blue;
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
  margin-top: 120px;
  height: 396px;
  width: 396px
}

.head {
  margin-top: 120px;
  padding-right: 34px;
  height: 376px;
  width: 376px
}
</style>
