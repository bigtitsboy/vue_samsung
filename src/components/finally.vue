<template>
  <div class="test" style="position: absolute">
    <div class="test imgdiv" style="border-radius: 2em;margin-right: 20px">
      <img :src="imgs[imgnum].path" @mouseenter="imgtouch" @mouseleave="imgleave">
    </div>
    <div class="test" style="margin: 2px;width: 654px;height: 684px;float: left">
      <div class="test touch" id="div1" style="margin-top: 80px" @mouseenter="over" ref="div0">
        <label for="div1" style="margin: 3px;display: inline-block;">
          <div class="test"
               style="font-weight: bold;font-size: 20px;line-height:50px;height: 50px;width: 50px;display: inline-block;vertical-align: middle">
            01
          </div>
          <div class="test"
               style="text-align:left;font-weight: bold;font-size: 25px;line-height:50px;height: 50px;width: 550px;display: inline-block;vertical-align: middle">
            <div style="margin-left: 50px">如何为宠物拍摄精彩影片</div>
          </div>
        </label>
        <div v-show="divshow[0].show" class="test"
             style="height: 100px;margin-left: 105px;text-align: left;border-bottom: 1px solid rgb(204, 204, 204)">
          <div
            style="margin-left: 20px;font-size: 15px;margin-top: 20px;text-decoration: underline;color: black;font-weight: bold">
            <a href="#" style="color: black;font-weight: bold">了解更多</a>
          </div>
        </div>
      </div>
      <div class="test leave" id="div2" @mouseenter="over" ref="div1">
        <label for="div2" style="margin: 3px;display: inline-block;">
          <div class="test"
               style="font-weight: bold;font-size: 20px;line-height:50px;height: 50px;width: 50px;display: inline-block;vertical-align: middle">
            02
          </div>
          <div class="test"
               style="text-align:left;font-weight: bold;font-size: 25px;line-height:50px;height: 50px;width: 550px;display: inline-block;vertical-align: middle">
            <div style="margin-left: 50px">折叠范儿，我的选择</div>
          </div>
        </label>
        <div v-show="divshow[1].show" class="test"
             style="height: 100px;margin-left: 105px;text-align: left;border-bottom: 1px solid rgb(204, 204, 204)">
          <div
            style="margin-left: 20px;font-size: 15px;margin-top: 20px;text-decoration: underline;color: black;font-weight: bold">
            <a href="#" style="color: black;font-weight: bold">了解更多</a>

          </div>
        </div>
      </div>
      <div class="test leave" id="div3" @mouseenter="over" ref="div2">
        <label for="div3" style="margin: 3px;display: inline-block;">
          <div class="test"
               style="font-weight: bold;font-size: 20px;line-height:50px; height: 50px;width: 50px;display: inline-block;vertical-align: middle">
            03
          </div>
          <div class="test"
               style="text-align:left;font-weight: bold;font-size: 25px;line-height:50px; height: 50px;width: 550px;display: inline-block;vertical-align: middle">
            <div style="margin-left: 50px">开箱一刻，探索无限</div>
          </div>
        </label>
        <div v-show="divshow[2].show" class="test"
             style="height: 100px;margin-left: 105px;text-align: left;border-bottom: 1px solid rgb(204, 204, 204)">
          <div
            style="margin-left: 20px;font-size: 15px;margin-top: 20px;text-decoration: underline;color: black;font-weight: bold;">
            <a href="#" style="color: black;font-weight: bold">了解更多</a>

          </div>
        </div>
      </div>
      <div class="test leave" id="div4" @mouseenter="over" ref="div3">
        <label for="div4" style="margin: 3px;display: inline-block;">
          <div class="test"
               style="font-weight: bold;font-size: 20px;line-height:50px;height: 50px;width: 50px;display: inline-block;vertical-align: middle">
            04
          </div>
          <div class="test"
               style="text-align:left;font-weight: bold;font-size: 25px;line-height:50px;height: 50px;width: 550px;display: inline-block;vertical-align: middle">
            <div style="margin-left: 50px">塑造一个更美好的地球</div>
          </div>
        </label>
        <div v-show="divshow[3].show" class="test"
             style="height: 100px;margin-left: 105px;text-align: left;border-bottom: 1px solid rgb(204, 204, 204)">
          <div
            style="margin-left: 20px;font-size: 15px;margin-top: 20px;text-decoration: underline;color: black;font-weight: bold">
            <a href="#" style="color: black;font-weight: bold">了解更多</a>

          </div>
        </div>
      </div>
      <div class="test leave" id="div5" @mouseenter="over" ref="div4">
        <label for="div5" style="margin: 3px;display: inline-block;">
          <div class="test"
               style="font-weight: bold;font-size: 20px;line-height:50px;height: 50px;width: 50px;display: inline-block;vertical-align: middle">
            05
          </div>
          <div class="test"
               style="text-align:left;font-weight: bold;font-size: 25px;line-height:50px;height: 50px;width: 550px;display: inline-block;vertical-align: middle">
            <div style="margin-left: 50px">The Voyage扬帆起航</div>
          </div>
        </label>
        <div v-show="divshow[4].show" class="test"
             style="height: 100px;margin-left: 105px;text-align: left;border-bottom: 1px solid rgb(204, 204, 204)">
          <div
            style="margin-left: 20px;font-size: 15px;margin-top: 20px;text-decoration: underline;color: black;font-weight: bold">
            <a href="#" style="color: black;font-weight: bold">了解更多</a>

          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'finally',
  data: function () {
    return {
      divshow: [
        { show: true },
        { show: false },
        { show: false },
        { show: false },
        { show: false }
      ],
      imgnum: 0,
      imgs: [
        { path: require('../assets/finally/img.png') },
        { path: require('../assets/finally/img.png') },
        { path: require('../assets/finally/img_1.png') },
        { path: require('../assets/finally/img_2.png') },
        { path: require('../assets/finally/img_3.png') },
        { path: require('../assets/finally/img_4.png') }
      ]
    }
  },
  methods: {
    imgleave: function (e) {
      e.target.className = 'imgleave'
    },
    imgtouch: function (e) {
      e.target.className = 'imgtouch'
    },
    over: function (e) {
      this.$refs.div0.className = 'test leave'
      this.$refs.div1.className = 'test leave'
      this.$refs.div2.className = 'test leave'
      this.$refs.div3.className = 'test leave'
      this.$refs.div4.className = 'test leave'
      e.target.className = 'test touch'
      var str = e.target.id.toString().slice(3, 4)
      this.imgnum = str
      this.divshow.forEach((child) => {
        child.show = false
        // console.log(child)
      })
      // console.log(this.imgnum)
      this.divshow[this.imgnum - 1].show = true
      // console.log(this.divshow[1].show)
    }
    // leave: function (e) {
    //
    // }
  }
}
</script>

<style scoped>

.imgdiv {
  margin: 2px;
  width: 684px;
  height: 684px;
  float: left;
  right: 100px;
  overflow: hidden
}

/*.test {*/
/*  border: 2px solid red;*/
/*}*/

.touch {
  border-top: 2px solid black;
  width: 645px;
  height: 170px;
  padding-top: 30px;
  margin: 2px 2px 20px;
}

.imgtouch {
  margin: -40px;
  height: 110%;
  width: 110%;
}

.imgleave {
  height: 100%;
  width: 100%;
}

.leave {
  width: 645px;
  height: 64px;
  margin: 2px 2px 20px;

}
</style>
