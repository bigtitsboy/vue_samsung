<template>
  <div>
    <el-header class="test" style="color: black;text-align: center">
      <div style="font-size: 38px;font-weight: bolder;margin-left: -40px">我们能帮忙找点什么吗?</div>
    </el-header>
    <el-header class="test" style="height: 200px">
      <div class="test" style="width: 605px;height: 160px;margin: 2px;padding: 2px;margin-left: 32%">
        <div class="test" style="width: 600px;height: 64px;">
          <div class="test"
               style="height: 48px ;width: 448px;display: inline-block;margin-top: 4px;border-radius: 2em;line-height: 48px;text-align: left;border:1px solid rgb(147, 147, 147);background-color: rgb(247, 247, 247)">
            <div class="test"
                 style="height: 24px;width: 24px;display: inline-block;vertical-align: middle;margin: 10px 10px 10px 20px;text-align: center;line-height: 26px">
              <i class="el-icon-search" style="font-weight: bolder;font-size: 20px"></i>
            </div>
            <input @focus="inputfocus" @blur="inputblur" type="text" v-model="inputvalue"
                   class="blur">
            <button v-show="buttonhide" @click="clear"
                    style="z-index:100;height:15px;width:15px;border-radius: 50%;text-align: center;margin-left: 5px;padding: 0px;border: none;background-color: rgb(143, 143, 143);cursor: pointer">
              <i class="el-icon-close" style="font-weight: bold;font-size: 3px;color: white"></i>
            </button>
          </div>
        </div>
        <div class="test" style="width: 600px;height: 80px;position: relative;margin-top: 4px">
          <div>
            <div style="font-size: 5px">
              <button class="searchbutton">Galaxy S21 Ultra 5G</button>
              <button class="searchbutton">Galaxy S21 | S21+ 5G</button>
              <button class="searchbutton">Galaxy Z Fold2 5G</button>
              <button class="searchbutton">Galaxy A52 5G</button>
            </div>
            <div>
              <button class="searchbutton">Samsung Galaxy Buds Pro</button>
              <button class="searchbutton">Samsung BESPOKE</button>
              <button class="searchbutton">衣物护理机</button>
            </div>
          </div>
        </div>
      </div>

    </el-header>
    <el-main class="test" style="margin-top: 2px;">
      <div class="test"
           style="height: 100px;width: 1220px;display: inline-block;font-size: 1px;text-align: left;color: black;font-weight: normal">
        *Galaxy A52 5G非专业防水手机，在正常使用状态下可防尘防水，实验室条件下测试效果达到 IEC 60529 标准界定的 IP67
        级别。IP67防浸水检测条件为：(1)无流动清水，水深1米；(2)试验时间30分钟；(3)水温与产品温差不大于5K。请严格按照产品说明书中有关防尘防水的说明使用，否则由此造成的设备损坏由使用者自行承担责任。不建议带入海滩、游泳池和肥皂水环境中使用。如果您不慎将含糖液体洒在手机上，请及时用清水湿巾擦拭
        。仅在低水压环境下保证设备安全。自来水或淋浴水等高水压环境可能会损坏设备。<br>
        <br>
        *本网站提供的屏幕和图像内容，是仅为说明目的而展示的模拟画面。产品图片以及型号、数据、功能、性能、规格参数、用户界面和其他产品信息等仅供参考，三星有可能对上述内容进行改进，具体信息请参照产品实物、产品说明书。除非经特殊说明，本网站中所涉及的数据均为三星内部测试结果，涉及的对比均为与三星产品相比较。
      </div>
    </el-main>
    <el-main name='erromain' class="test1"
             style="position: absolute;margin-left: 180px;text-align: left;color: black;padding-left: 20px;width: 1520px">
      <div class="test1"
           style="height: 641px;width: 330px;float: left;color: black;padding-left: 20px;border-top: 1px solid rgb(204, 204, 204);border-bottom: 1px solid rgb(204, 204, 204);border-right: 1px solid rgb(204, 204, 204)">
        <h3>产品与服务</h3>
        <a v-for="(item,index) in button1texts" :key="index" href="#"
        >{{
            item
          }}</a>
      </div>
      <div class="test1"
           style="height: 641px;width: 330px;float: left;color: black;padding-left: 20px;border-top: 1px solid rgb(204, 204, 204);border-bottom: 1px solid rgb(204, 204, 204)">
        <h3>购买渠道</h3>
        <a v-for="(item,index) in button2texts" :key="index" href="#" v-html="item"
        ></a>
      </div>
      <div class="test1"
           style="height: 641px;width: 330px;float: left;color: black;padding-left: 20px;border-top: 1px solid rgb(204, 204, 204);border-bottom: 1px solid rgb(204, 204, 204);border-left: 1px solid rgb(204, 204, 204)">
        <h3>服务支持</h3>
        <a v-for="(item,index) in button3texts" :key="index" href="#"
        >{{
            item
          }}</a>
      </div>
      <div class="test1"
           style="height: 641px;width: 330px;float: left;color: black;padding-left: 20px;border-top: 1px solid rgb(204, 204, 204);border-bottom: 1px solid rgb(204, 204, 204);border-left: 1px solid rgb(204, 204, 204)">
        <h3>可持续发展</h3>
        <a v-for="(item,index) in button4texts" :key="index" href="#"
        >{{
            item
          }}</a>
        <h3>关于我们</h3>
        <a v-for="(item,index) in button5texts" :key="index" href="#" v-html="item"
        ></a>
      </div>
      <el-header
        style="border-bottom: 1px solid rgb(204, 204, 204);float: left;height: 60px;width: 1405px;margin-top: 30px">
        <div style="font-size: 1px;color: black">© 1995-2021 三星（中国）投资有限公司 版权所有</div>
        <div>
          <a style="text-decoration: none;display: inline;font-size: 1px;color: blue" href="#">京ICP备05068163号</a>
          <a style="text-decoration: none;display: inline;font-size: 1px;color: blue;margin-left: 5px" href="#">京公网安备11010502040099号</a>
        </div>
      </el-header>
      <el-header
        style="float: left;height: 34px;width: 1405px;margin-top: 10px;padding-top: 10px;">
        <div style="position: absolute;height: 34px;width: 1380px;line-height: 30px">
          <a style="display: inline;margin-left: 0px;font-size: 5px;font-weight: bolder;border-right: 1px solid rgb(204, 204, 204);padding-right: 25px" href="#">中国大陆/中文</a>
          <a style="display: inline;margin-left: 20px;font-size: 5px;" href="#">辅助功能</a>
          <a style="display: inline;margin-left: 20px;font-size: 5px;" href="#">网站地图</a>
          <a style="display: inline;margin-left: 20px;font-size: 5px;" href="#">服务条款</a>
          <a style="display: inline;margin-left: 20px;font-size: 5px;" href="#">重要声明</a>
          <a style="display: inline;margin-left: 20px;font-size: 5px;" href="#">隐私政策</a>
          <div style=";font-size: 5px;float: right;">
            官方分享
            <div style="display: inline-block;">
              <i style="font-weight: bolder;font-size: 25px;margin-left: 10px;" class="el-icon-message"></i>
              <i style="font-weight: bolder;font-size: 25px;margin-left: 20px;" class="el-icon-headset"></i>
            </div>

          </div>
        </div>
      </el-header>
    </el-main>
  </div>
</template>

<script>
export default {
  name: 'search',
  data: function () {
    return {
      button5texts: [
        '公司介绍',
        '业务范围',
        '品牌标识',
        '人才招聘',
        '投资者关系<i class="el-icon-top-right"></i>',
        '新闻中心',
        '伦理道德',
        '三星设计<i class="el-icon-top-right"></i>'
      ],
      button4texts: [
        '概览',
        '环境',
        '企业公民',
        '数字责任',
        '劳工与人权',
        '多元化与包容性',
        '可持续供应链'
      ],
      button3texts: [
        '在线服务',
        '邮件咨询',
        '联系我们',
        '服务中心查询'
      ],
      button2texts: [
        '最新活动',
        '网上商城 <i class="el-icon-top-right"></i>',
        '三星Galaxy 授权体验店',
        '全产品门店查询',
        '电视/影音产品门店查询',
        '冰箱/洗衣机产品门店查询',
        '7D机',
        '官方翻新机'
      ],
      button1texts: [
        '智能手机',
        '智能平板',
        '音频产品',
        '智能手表',
        'S 换机助手',
        '智能产品配件',
        '电视',
        '冰箱',
        '洗衣机',
        '空调',
        '显示器',
        '存储产品'
      ],
      buttonhide: false,
      inputvalue: ''
    }
  },
  methods: {
    clear: function () {
      // console.log(1)
      this.inputvalue = ''
      this.buttonhide = false
    },
    inputblur: function (e) {
      // console.log(this.inputvalue.length !== 0)
      // console.log(this.inputvalue.length)
      if (this.inputvalue.length !== 0) {
        this.buttonhide = true
      } else {
        this.buttonhide = false
      }
      e.target.className = 'blur'
    },
    inputfocus: function (e) {
      this.buttonhide = true
      e.target.className = 'focus'
    }
  }
}
</script>

<style scoped>
/*.test {*/
/*  border: 2px solid red;*/
/*}*/
/*.test1 {*/
/*  border: 2px solid red;*/
/*}*/

a {
  display: block;
  height: 32px;
  width: 359px;
  color: black;
  text-decoration: none;
  font-size: 14px
}

input:focus {
  outline: medium;
}

a:hover {
  display: block;
  height: 32px;
  width: 359px;
  color: blue;
  text-decoration: underline;
  font-size: 14px
}

.searchbutton {
  font-weight: initial;
  line-height: 32px;
  border: 1px solid rgb(204, 204, 204);
  font-size: 11px;
  padding: 0px 15px 0px 15px;
  margin-left: 10px;
  margin-top: 4px;
  background-color: white;
  color: black;
  border-radius: 2em;
}

.focus {
  background-color: rgb(247, 247, 247);
  margin-left: 2px;
  height: 24px;
  width: 334px;
  border: 1px dashed black
}

.blur {
  background-color: rgb(247, 247, 247);
  margin-left: 2px;
  height: 24px;
  width: 334px;
  border: none
}
</style>
