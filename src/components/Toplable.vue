<template>
  <div>
    <el-row>
      <el-container>
        <el-header class="logo">
          <el-col :span="12" style="padding-left: 10% ;line-height: 80px;">
            <img :src="myimgs[0].path" style="float: left;padding-top: 27px;padding-right: 50px">
            <ul>
              <li v-for="(item,index) in head1" :key="item"
                  style="font-size: 15px;font-weight: bolder;margin-right: 20px">
                <span @mouseenter="spanchange($event),listshow(index+1)" :ref="item.slice(0,2)" v-html="item"
                      class="spanleave">
                </span>
              </li>
              <!--              <div style="clear:both;"></div>-->
              <!--                <m1 v-show="m1show" style="position: absolute;z-index: 1000;margin-top: 50px;margin-left: -19.3%"></m1>-->
            </ul>
          </el-col>
          <el-col :span="12" style="padding-right: 15%;text-align: right;line-height: 80px">
            <ul style="float: right" @mouseleave="spanclear">
              <li v-for="(item) in head2" :key="item" style="font-size: 15px;font-weight: bolder;margin-right: 20px">
                <span @mouseenter="spanchange" :ref="item.slice(0,2)" v-html="item"
                      class="spanleave"></span>
              </li>
              <i style="font-size: 20px" class="el-icon-search ico"></i>
              <!--              <div v-html="html1"></div>-->
              <div style="clear:both;"></div>
            </ul>
            <!--            <i class="el-icon-shopping-cart-2 ico"></i>-->
            <!--            <i class="el-icon-s-grid ico"></i>-->
          </el-col>
        </el-header>
        <M1 @listleave="listleave" v-show="m1show" style="position: absolute;z-index: 1000;margin-top: 110px;"></M1>
        <M2 @mouseleave.native="listleave" v-show="m2show" style="position: absolute;z-index: 1000;margin-top: 110px;"></M2>
        <M3 @mouseleave.native="listleave" v-show="m3show" style="position: absolute;z-index: 1000;margin-top: 110px;"></M3>
        <M4 @mouseleave.native="listleave" v-show="m4show" style="position: absolute;z-index: 1000;margin-top: 110px;"></M4>
      </el-container>
    </el-row>
    <el-row>
      <el-container>
        <transition name="turn">
          <!--        <transition enter-active-class="animate__animated animate__fadeIn"-->
          <!--                    leave-active-class="animate__animated animate__fadeOut" >-->
          <div v-show="flag" style="z-index: 90" @mouseenter="enter" @mouseleave="leave">
            <el-main style="position: absolute;margin: 5px 10% 5px 9%">
              <el-button @click="less" circle icon="el-icon-arrow-left"
                         style="position: absolute;left: 2%;top: 50%;opacity: 0.5;background-color: black;color: white;z-index: 100"></el-button>
              <img :src="turnurl" style="margin-top: 50px" alt="" width="100%" height="100%">
              <!--            <transition name="turn">-->
              <!--              <img v-show="flag" :src="turnurl" alt="" width="100%" height="100%">-->
              <!--            </transition>-->
              <el-button @click="add" circle icon="el-icon-arrow-right"
                         style="position: absolute;right: 2%;top: 50%;opacity: 0.5;background-color: black;color: white;z-index: 100"></el-button>
            </el-main>
          </div>
        </transition>
      </el-container>
    </el-row>
    <el-row>
      <el-container>
        <el-header style="position: relative;margin: 45% 10% 5px 40%">
          <div style="position: absolute;font-size: 40px;color: black;"><strong style="padding-left: 80px">移动产品</strong>
          </div>
        </el-header>
      </el-container>
    </el-row>
    <el-row>
      <el-container>
        <el-col :span="23">
          <div style="margin-top: 10px">
            <button
              id="0"
              class="probutton"
              ref="q"
              @click="changeclss">
              Galaxy Z Fold2 5G | Z Flip 5G
            </button>
            <button
              id="1"
              class="probutton"
              ref="w"
              @click="changeclss">
              Galaxy A52 5G
            </button>
            <button
              id="2"
              class="probutton"
              ref="e"
              @click="changeclss">
              Galaxy S21 Ultra 5G
            </button>
            <button
              id="3"
              class="probutton"
              ref="r"
              @click="changeclss">
              Galaxy F52 5G
            </button>
            <button
              id="4"
              class="probutton"
              ref="t"
              @click="changeclss">
              北京国际电影节
            </button>
          </div>
        </el-col>
      </el-container>
    </el-row>
    <el-row>
      <el-container>
        <div>
          <el-main style="width: 1800px;">
            <img :src="phoneimgs[buttonindex].path">
          </el-main>
        </div>
      </el-container>
    </el-row>
    <el-row>
      <el-container>
        <el-col>
          <div style="font-weight: bolder;font-size: 40px;color: black">{{ phonetexts[buttonindex].test }}</div>
          <div style="color: black;font-size: 20px">{{ phonetexts[buttonindex].test1 }}</div>
          <div style="margin-top: 10px">
            <a style="text-decoration: underline black" href="https://www.samsung.com/cn/smartphones/galaxy-z/">
              <div style="color: black;font-weight:bold">
                <strong @mouseover="buychangein" @mouseleave="buychangeout">{{ phonetexts[buttonindex].first }}</strong>
                <el-button round style="margin-left: 20px;background-color: black;color: white">
                  <div @mouseover="buychangein" @mouseleave="buychangeout">
                    {{ phonetexts[buttonindex].second }}
                    <i class="el-icon-top-right"></i>
                  </div>
                </el-button>
              </div>
            </a>
          </div>
        </el-col>
      </el-container>
    </el-row>
    <el-row>
      <el-container>
        <el-main>
          <div style="position: relative;">
            <div style="position: absolute;left:45%;top: 100px;color: white;font-size: 40px;font-weight: bold">
              电视/影音
            </div>
            <div style="position: absolute;left:14%;top: 150px;color: white;font-size: 40px;font-weight: bold">
              <button class="tvbotton" name="0"
                      ref="a"
                      @click="tvchangeclss">三星Neo QLED 8K电视QN900A
              </button>
              <button class="tvbotton" name="1"
                      ref="s"
                      @click="tvchangeclss">三星Neo QLED电视QN85A
              </button>
              <button class="tvbotton" name="2"
                      ref="d"
                      @click="tvchangeclss">画壁系列融入屏
              </button>
              <button class="tvbotton" name="3"
                      ref="f"
                      @click="tvchangeclss">The Premiere绚幕系列激光投影仪
              </button>
              <button class="tvbotton" name="4"
                      ref="g"
                      @click="tvchangeclss">回音壁条形音响 HW-Q950T
              </button>
            </div>
            <div
              style="position: absolute;left:32%;top: 650px;color: white;font-size: 40px;font-weight: bold;display: inline-block;height: 136px;width: 690px;text-align: center;margin-top: 30px">
              <div style="font-weight: bolder;font-size: 40px;color: white">{{ tvtexts[tvbuttonindex].text }}</div>
              <div style="color: white;font-size: 20px">{{ tvtexts[tvbuttonindex].text1 }}</div>
              <div style="margin-top: 10px">
                <a style="text-decoration: underline black" href="https://www.samsung.com/cn/smartphones/galaxy-z/">
                  <div style="color: white;font-weight:bold;">
                    <strong @mouseover="buychangein" @mouseleave="buychangeout"
                            style="font-size: 15px;text-decoration: underline">{{
                        tvtexts[tvbuttonindex].first
                      }}</strong>
                    <el-button round style="margin-left: 20px;background-color: white;color: black">
                      <div @mouseover="buychangein" @mouseleave="buychangeout"
                           style="font-size: 10px;font-weight: bold">
                        {{ tvtexts[tvbuttonindex].second }}
                        <i class="el-icon-top-right"></i>
                      </div>
                    </el-button>
                  </div>
                </a>
              </div>
            </div>
            <img :src="tvimgs[tvbuttonindex].path" alt=""
                 style="padding-top: 40px;height:806px;width: 1437px;background-color: white ">
          </div>
        </el-main>
      </el-container>
    </el-row>
    <el-row>
      <el-container>
        <el-main>
          <div style="position: relative;">
            <div ref="h" class="headblack">
              生活家电
            </div>
            <div style="position: absolute;left:34%;top: 120px;color: white;font-size: 40px;font-weight: bold">
              <button class="homebottonblack" name="0"
                      ref="z"
                      @click="homechangeclss">冰箱
              </button>
              <button class="homebottonblack" name="1"
                      ref="x"
                      @click="homechangeclss">洗衣机/衣物护理机

              </button>
              <button class="homebottonblack" name="2"
                      ref="c"
                      @click="homechangeclss"> 空气净化器

              </button>
              <button class="homebottonblack" name="3"
                      ref="v"
                      @click="homechangeclss">智能吸尘器

              </button>
              <button class="homebottonblack" name="4"
                      ref="b"
                      @click="homechangeclss"> 空调

              </button>
            </div>
            <div
              ref="detail" class="detailblack">
              <div style="font-size: 50px;">{{
                  hometests[homebuttonindex].text
                }}<br>{{ hometests[homebuttonindex].text1 }}
              </div>
              <!--              <div style="color: white;font-size: 20px">{{ hometests[homebuttonindex].text1 }}</div>-->
              <div style="margin-top: 10px">
                <a style="text-decoration: underline black" href="https://www.samsung.com/cn/smartphones/galaxy-z/">
                  <div style="font-weight:bold;">
                    <strong class="firstblack" ref="first" @mouseover="buychangein" @mouseleave="buychangeout"
                    >{{
                        hometests[homebuttonindex].first
                      }}</strong>
                    <button ref="secondbutton" class="secondbuttonblack">
                      <div class="secondblack" ref="second" @mouseover="buychangein" @mouseleave="buychangeout"
                      >
                        {{ hometests[homebuttonindex].second }}
                        <i class="el-icon-top-right"></i>
                      </div>
                    </button>
                  </div>
                </a>
              </div>
            </div>
            <img :src="homeimgs[homebuttonindex].path" alt=""
                 style="padding-top: 40px;height:806px;width: 1437px;background-color: white ">
          </div>
        </el-main>
      </el-container>
    </el-row>
    <el-row>
      <el-container>
        <el-header style="margin: 10px;height: 150px">
          <div style="margin-top: 2px"><h1 style="font-size: 40px;color: black">本月精选</h1></div>
          <button ref="button1" name="1" @click="buttonchange" class="changebutton">最新活动</button>
          <button ref="button2" name="2" @click="buttonchange" class="changebutton">手机/平板</button>
          <button ref="button3" name="3" @click="buttonchange" class="changebutton"> 电视/影音</button>
          <button ref="button4" name="4" @click="buttonchange" class="changebutton"> 家电/智家</button>
        </el-header>
        <el-header style="height: 700px;width: 1420px;margin: 10px 240px 10px 240px;">
          <div style="margin-top: 0px">
            <transition name="my">
              <first :key="'t1'" v-show="fistclick"></first>
            </transition>
            <transition-group>
              <second :key="'t2'" v-show="secondclick"></second>
              <third :key="'t3'" v-show="thirdclick"></third>
              <fourth :key="'t4'" v-show="fourthclick"></fourth>
            </transition-group>
          </div>
        </el-header>
        <!--        <button style="z-index: 100" @click="fistclick=!fistclick">fade</button>-->
      </el-container>
    </el-row>
    <el-row class="test" style="margin-top: 140px">
      <el-container>
        <el-header class="test" style="margin: 2px;font-size: 40px;font-weight: bolder;color: black">Explore
          #DoWhatYouCant
        </el-header>
        <el-header class="test" style="margin: 2px;"><a href="https://www.samsung.com/cn/explore/"
                                                        style="text-decoration: underline;color: black">查看更多</a>
        </el-header>
        <el-main class="test" style="width: 1392px;height: 766px;margin: 2px 2px 2px 255px;">
          <finally style="color: black"></finally>
        </el-main>
      </el-container>
    </el-row>
    <el-row class="test1" style="margin-top: 60px">
      <el-container>
        <el-main style="width: 1900px;height: 500px;margin: 2px 2px 2px 2px">
          <search></search>
        </el-main>
      </el-container>
    </el-row>
  </div>
</template>

<script>
import first from '@/components/first'
import Second from '@/components/second'
import Third from '@/components/third'
import Fourth from '@/components/fourth'
import Finally from '@/components/finally'
import Search from '@/components/search'
import 'animate.css'
import M1 from '@/components/m1'
import M2 from '@/components/m2'
import M3 from '@/components/m3'
import M4 from '@/components/m4'

export default {
  data: function () {
    return {
      m1show: false,
      m2show: false,
      m3show: false,
      m4show: false,
      // html1: '<i style="font-size: 20px" class="el-icon-search ico"></i>',
      head1: [
        '手机/平板',
        '电视/影音',
        '家电/智家',
        '电脑/办公/存储',
        '最新活动'
      ],
      head2: [
        'Explore',
        '网上商城' + '<i  class="el-icon-top-right ico"></i>',
        '售后服务',
        '商用解决方案'
      ],
      flag: true,
      fistclick: true,
      secondclick: false,
      thirdclick: false,
      fourthclick: false,
      homebuttonindex: 0,
      homeimgs: [
        { path: require('../assets/home/img.png') },
        { path: require('../assets/home/img_1.png') },
        { path: require('../assets/home/img_2.png') },
        { path: require('../assets/home/img_3.png') },
        { path: require('../assets/home/img_4.png') }
      ],
      hometests: [
        {
          text: 'Samsung BESPOKE灵变·炫彩系列冰箱',
          text1: '',
          first: '了解更多',
          second: '门店查询'
        },
        {
          text: '灵净·呵护系列',
          text1: '衣物护理机',
          first: '了解更多',
          second: '门店查询'
        },
        {
          text: '洁净看得见 舒心大空间',
          text1: '',
          first: '',
          second: '了解更多'
        },
        {
          text: '强劲 持久 轻巧 便捷',
          text1: '',
          first: '',
          second: '了解更多'
        },
        {
          text: '风之交响 畅享四季',
          text1: '',
          first: '',
          second: '了解更多'
        }
      ],
      tvtexts: [
        {
          text: '三星Neo QLED 8K电视QN900A',
          text1: '真撼于·新',
          first: '了解更多',
          second: '立即抢购'
        }, {
          text: '三星Neo QLED电视QN85A',
          text1: '纤薄设计 精准光控 ',
          first: '了解更多',
          second: '立即抢购'
        }, {
          text: '画壁系列融入屏',
          text1: '',
          first: '了解更多',
          second: '立即购买'
        }, {
          text: 'The Premiere绚幕系列激光投影仪',
          text1: '',
          first: '',
          second: '了解更多'
        },
        {
          text: '回音壁条形音响 HW-Q950T',
          text1: '',
          first: '了解更多',
          second: '立即购买'
        }
      ],
      tvimgs: [
        { path: require('../assets/tv/img.png') },
        { path: require('../assets/tv/img_1.png') },
        { path: require('../assets/tv/img_2.png') },
        { path: require('../assets/tv/img_3.png') },
        { path: require('../assets/tv/img_4.png') }
      ],
      phonetexts: [
        {
          first: '了解更多',
          second: '立即抢购',
          buy: 'https://www.samsungeshop.com.cn/activitys/galaxyFoldable',
          test: 'Galaxy Z Fold2 5G | Z Flip 5G',
          test1: '引领折叠屏新未来',
          url: 'https://www.samsung.com/cn/smartphones/galaxy-z/'
        },
        {
          first: '了解更多',
          second: '立即抢购',
          buy: 'https://www.samsungeshop.com.cn/product/SM-A5260/SM-A5260ZKGCHC',
          test: 'Galaxy A52 5G',
          test1: '新品上市',
          url: 'https://www.samsung.com/cn/smartphones/galaxy-a/galaxy-a52-5g-awesome-black-256gb-sm-a5260zkhchc/'
        },
        {
          first: '了解更多',
          second: '立即抢购',
          buy: 'https://www.samsungeshop.com.cn/product/SM-G9980/SM-G9980ZKGCHC',
          test: 'Galaxy S21 Ultra 5G',
          test1: '震撼上市 火热抢购中',
          url: 'https://www.samsung.com/cn/smartphones/galaxy-s21-ultra-5g/'
        },
        {
          first: '了解更多',
          second: '立即预定',
          buy: 'https://www.samsungeshop.com.cn/product/SM-E5260/SM-E5260ZKDCHC',
          test: 'Galaxy F52 5G',
          test1: '享3期0利率 赠好礼',
          url: 'https://www.samsung.com/cn/smartphones/galaxy-f/galaxy-f52-5g-black-128gb-sm-e5260zkdchc/'
        },
        {
          first: '',
          second: '了解更多',
          test: '北京国际电影节',
          test1: '三星手机电影短片单元',
          url: 'https://support-cn.samsung.com/campaign/mobilephone/GalaxyS21/dyj/index.html'
        }
      ],
      show3: true,
      tvbuttonindex: 0,
      buttonindex: 0,
      phoneimgs: [
        { path: require('../assets/phone/img.png') },
        { path: require('../assets/phone/img_1.png') },
        { path: require('../assets/phone/img_2.png') },
        { path: require('../assets/phone/img_3.png') },
        { path: require('../assets/phone/img_4.png') }
      ],
      turninerval: null,
      turnsum: 0,
      turnurl: 0,
      myimgs: [
        { path: require('../assets/sumsung.png') }
      ],
      turnimgs: [
        {
          path: require('../assets/turnimg/img.png')
        },
        {
          path: require('../assets/turnimg/img_1.png')
        },
        {
          path: require('../assets/turnimg/img_2.png')
        }
      ]
    }
  },
  // head1: [
  //   '手机/平板',
  //   '电视/影音',
  //   '家电/智家',
  //   '电脑/办公/存储',
  //   '最新活动'
  // ],
  // head2: [
  //   'Explore',
  //   '网上商城' + '<i  class="el-icon-top-right ico"></i>',
  //   '售后服务',
  //   '商用解决方案'
  // ],
  methods: {
    listleave: function (e) {
      // console.log(e.target.getAttribute('name'))
      this.m1show = false
      this.m2show = false
      this.m3show = false
      this.m4show = false
      // console.log(e.target.style)
      // e.target.style.display = 'none'
      this.$refs.手机[0].className = 'spanleave'
      this.$refs.电视[0].className = 'spanleave'
      this.$refs.家电[0].className = 'spanleave'
      this.$refs.电脑[0].className = 'spanleave'
      this.$refs.最新[0].className = 'spanleave'
      this.$refs.Ex[0].className = 'spanleave'
      this.$refs.网上[0].className = 'spanleave'
      this.$refs.售后[0].className = 'spanleave'
      this.$refs.商用[0].className = 'spanleave'
    },
    // m1show: false,
    // m2show: false,
    // m3show: false,
    // m4show: false,
    listshow: function (index) {
      this.m1show = false
      this.m2show = false
      this.m3show = false
      this.m4show = false
      switch (index) {
        case 1:
          this.m1show = true
          break
        case 2:
          this.m2show = true
          break
        case 3:
          this.m3show = true
          break
        case 4:
          this.m4show = true
          break
        case 5:
          break
      }
    },
    spanclear: function (e) {
      this.$refs.手机[0].className = 'spanleave'
      this.$refs.电视[0].className = 'spanleave'
      this.$refs.家电[0].className = 'spanleave'
      this.$refs.电脑[0].className = 'spanleave'
      this.$refs.最新[0].className = 'spanleave'
      this.$refs.Ex[0].className = 'spanleave'
      this.$refs.网上[0].className = 'spanleave'
      this.$refs.售后[0].className = 'spanleave'
      this.$refs.商用[0].className = 'spanleave'
      // this.m1show = !this.m1show
    },
    spanchange: function (e) {
      this.$refs.手机[0].className = 'spanleave'
      this.$refs.电视[0].className = 'spanleave'
      this.$refs.家电[0].className = 'spanleave'
      this.$refs.电脑[0].className = 'spanleave'
      this.$refs.最新[0].className = 'spanleave'
      this.$refs.Ex[0].className = 'spanleave'
      this.$refs.网上[0].className = 'spanleave'
      this.$refs.售后[0].className = 'spanleave'
      this.$refs.商用[0].className = 'spanleave'
      e.target.className = 'spantouch'
      // this.m1show = !this.m1show
      // this.head1.forEach((item) => {
      //   // console.log(item)
      //   console.log(this.$refs.item)
      // })
      // this.$refs.
      // console.log(this.$refs)
      // var mystring1 = this.head1[0]
      // console.log(this.$refs)
      // console.log(this.$refs.售后服务[0])
      // console.log(this.$refs.售后服务[0].className)
    },
    buttonchange: function (e) {
      this.$refs.button1.className = 'changebutton'
      this.$refs.button2.className = 'changebutton'
      this.$refs.button3.className = 'changebutton'
      this.$refs.button4.className = 'changebutton'
      e.target.className = 'changebuttontouch'
      switch (e.target.name) {
        case '1':
          this.fistclick = true
          this.secondclick = false
          this.thirdclick = false
          this.fourthclick = false
          break
        case '2':
          this.fistclick = false
          this.secondclick = true
          this.thirdclick = false
          this.fourthclick = false
          break
        case '3':
          this.fistclick = false
          this.secondclick = false
          this.thirdclick = true
          this.fourthclick = false
          break
        case '4':
          this.fistclick = false
          this.secondclick = false
          this.thirdclick = false
          this.fourthclick = true
          break
        default:
          this.fistclick = true
      }
    },
    homechangeclss: function (e) {
      // this.show3 = !this.show3 0_4
      this.homebuttonindex = e.target.name
      // console.log(parseInt(e.target.name) !== 0)
      // console.log(typeof e.target.name)
      if (parseInt(e.target.name) === 0 || parseInt(e.target.name) === 4) {
        this.$refs.z.className = 'homebottonblack'
        this.$refs.x.className = 'homebottonblack'
        this.$refs.c.className = 'homebottonblack'
        this.$refs.v.className = 'homebottonblack'
        this.$refs.b.className = 'homebottonblack'
      } else {
        this.$refs.z.className = 'homebottonwhite'
        this.$refs.x.className = 'homebottonwhite'
        this.$refs.c.className = 'homebottonwhite'
        this.$refs.v.className = 'homebottonwhite'
        this.$refs.b.className = 'homebottonwhite'
        // console.log(e.target)
      }
      // console.log(this.homebuttonindex)
      // console.log(this.$refs)
      // for (const key in this.$refs) {
      //   this.$refs[key].className = 'tvprobutton'
      // }
      if (parseInt(e.target.name) !== 0 && parseInt(e.target.name) !== 4) {
        e.target.className = 'homeselectshite'
        this.$refs.h.className = 'headwhite'
        this.$refs.detail.className = 'detailwhite'
        // console.log(e.target)
      } else {
        this.$refs.detail.className = 'detailblack'
        e.target.className = 'homeselect'
        this.$refs.h.className = 'headblack'
      }
      if (parseInt(e.target.name) !== 0 && parseInt(e.target.name) !== 3 && parseInt(e.target.name) !== 4) {
        this.$refs.detail.className = 'detailwhite'
        // console.log(e.target)
      } else {
        this.$refs.detail.className = 'detailblack'
      }
      if (parseInt(e.target.name) !== 1 && parseInt(e.target.name) !== 2) {
        this.$refs.first.className = 'firstblack'
        this.$refs.second.className = 'secondblack'
        this.$refs.secondbutton.className = 'secondbuttonblack'
        // console.log(e.target)
      } else {
        this.$refs.second.className = 'secondwhite'
        this.$refs.first.className = 'firstwhite'
        this.$refs.secondbutton.className = 'secondbuttonwhite'
      }
    },
    tvchangeclss: function (e) {
      // this.show3 = !this.show3
      this.tvbuttonindex = e.target.name
      console.log(this.tvbuttonindex)
      // console.log(this.$refs)
      this.$refs.a.className = 'tvprobutton'
      this.$refs.s.className = 'tvprobutton'
      this.$refs.d.className = 'tvprobutton'
      this.$refs.f.className = 'tvprobutton'
      this.$refs.g.className = 'tvprobutton'
      // for (const key in this.$refs) {
      //   this.$refs[key].className = 'tvprobutton'
      // }
      e.target.className = 'tvselect'
    },
    buychangein: function (e) {
      e.target.style.opacity = 0.5
    },
    buychangeout: function (e) {
      e.target.style.opacity = 1
    },
    changeclss: function (e) {
      this.show3 = !this.show3
      this.buttonindex = e.target.id
      // console.log(this.buttonindex)
      // console.log(this.$refs)
      this.$refs.q.className = 'probutton'
      this.$refs.w.className = 'probutton'
      this.$refs.e.className = 'probutton'
      this.$refs.r.className = 'probutton'
      this.$refs.t.className = 'probutton'
      // for (const key in this.$refs) {
      //   this.$refs[key].className = 'probutton'
      // }
      e.target.className = 'select'
    },
    add: function () {
      this.interval()
      // console.log(this.turnsum)
      // this.turnurl = this.turnimgs[this.turnsum].path
      // console.log(this.turnimgs.next)
      // window.clearInterval(this.turninerval)
      // console.log(1)
      // console.log(this.turnsum)
      // this.turnsum++
      // if (this.turnsum === 3) {
      //   this.turnsum = 0
      // }
      // switch (this.turnsum) {
      //   case 0:
      //     console.log(this.turnsum)
      //     this.turnsum = 0
      //     this.turnurl = this.turnimgs[this.turnsum].path
      //     // this.turninerval = setInterval(this.interval, 2500)
      //     break
      //   case 1:
      //     console.log(this.turnsum)
      //     this.turnsum = 1
      //     this.turnurl = this.turnimgs[this.turnsum].path
      //
      //     // this.turninerval = setInterval(this.interval, 2500)
      //     break
      //   case 2:
      //     console.log(this.turnsum)
      //     this.turnsum = 2
      //     this.turnurl = this.turnimgs[this.turnsum].path
      //     // this.turninerval = setInterval(this.interval, 2500)
      //     break
    },
    less: function () {
      // console.log(this.turnsum)
      // this.turnurl = this.turnimgs[this.turnsum].path
      // window.clearInterval(this.turninerval)
      // console.log(1)
      // console.log(this.turnsum)
      // this.turnsum -= 2
      // if (this.turnsum === 0) {
      //   this.turnsum = 1
      // }
      // if (this.turnsum === 2) {
      //   this.turnsum = 0
      // }
      // if (this.turnsum === 1) {
      //   this.turnsum = 2
      // }
      switch (this.turnsum) {
        case 0:
          this.turnsum = 1
          this.interval()
          // console.log(this.turnsum)
          // this.turnurl = this.turnimgs[this.turnsum].path
          // this.turninerval = setInterval(this.interval, 2500)
          break
        case 1:
          this.turnsum = 2
          // this.turnurl = this.turnimgs[this.turnsum].path
          this.interval()

          // console.log(this.turnsum)
          // this.turninerval = setInterval(this.interval, 2500)
          break
        case 2:
          this.turnsum = 0
          // this.turnurl = this.turnimgs[this.turnsum].path
          this.interval()

          // console.log(this.turnsum)
          // this.turninerval = setInterval(this.interval, 2500)
          break
      }
    },
    enter: function () {
      clearInterval(this.turninerval)
    },
    leave: function () {
      // clearInterval(this.turninerval)
      // this.interval()
      this.turninerval = setInterval(this.interval, 5000)
    },
    // interval1: function () {
    //   console.log(1)
    //   if (this.turnsum < this.turnimgs.length) {
    //     this.turnurl = this.turnimgs[this.turnsum].path
    //     this.turnsum++
    //     if (this.turnsum === 3) {
    //       this.turnsum = 0
    //     }
    //     // console.log(this.turnsum)
    //   }
    // },
    interval: function () {
      if (this.turnsum < this.turnimgs.length) {
        this.flag = !this.flag
        setTimeout(() => {
          this.flag = !this.flag
          this.turnurl = this.turnimgs[this.turnsum].path
          this.turnsum++
          if (this.turnsum === 3) {
            this.turnsum = 0
          }
        }, 300)
        // console.log(this.turnsum)
      }
      // if (this.turnsum < this.turnimgs.length) {
      //   this.turnurl = this.turnimgs[this.turnsum].path
      //   this.turnsum++
      //   if (this.turnsum === 3) {
      //     this.turnsum = 0
      //   }
      //   // console.log(this.turnsum)
      // }
    }
  },
  components: {
    M4,
    M3,
    M2,
    M1,
    Search,
    Finally,
    Fourth,
    Third,
    Second,
    first
  },
  created () {
    this.turnurl = this.turnimgs[this.turnsum].path
    this.turnsum++
  },
  mounted () {
    this.turninerval = setInterval(this.interval, 5000)
  }
}
</script>

<style scoped>
* {
  margin: 0;
  padding: 0;
}

.spantouch {
  cursor: pointer;
  padding: 6px 12px;
  border-radius: 2em;
  background-color: black;
  color: white
}

.spanleave {
  cursor: pointer;
  padding: 6px 12px;
  /*border-radius: 2em;*/
  /*background-color: black;*/
  /*color: white*/
}

ul {
  padding: 0;
  margin: 0;
  float: left;
}

li {
  padding: 0;
  margin: 0;
  list-style: none;
  /*float: left;*/
  display: inline;
  vertical-align: middle
}

.turn-enter,
.turn-leave-to {
  opacity: 0;
}

.turn-enter-active,
.turn-leave-active {
  transition: all 0.5s ease;
}

.my-enter {
  opacity: 0;
  transform: translateX(-1420px);
}

.my-leave-to {
  opacity: 0;
  transform: translateX(-1420px);
}

.my-enter-active,
.my-leave-active {
  transition: all 0.5s ease;
}

.v-leave-to {
  opacity: 0;
  transform: translateX(-1420px);
}

.v-enter {
  opacity: 0;
  transform: translateX(1420px);
}

.v-enter-active,
.v-leave-active {
  transition: all 0.5s ease;
}

.changebuttontouch {
  text-decoration: underline;
  cursor: pointer;
  border: 2px dashed black;
  background-color: transparent;
  height: 35px;
  margin-top: 10px;
  margin-left: 45px;
  font-size: 20px;
  color: black;
  font-weight: bolder;
}

.changebutton {
  cursor: pointer;
  border: none;
  background-color: transparent;
  height: 35px;
  margin-top: 10px;
  margin-left: 45px;
  font-size: 20px;
  color: black;
  font-weight: bolder;
}

.secondbuttonwhite {
  cursor: pointer;
  border: none;
  border-radius: 25px;
  width: 112px;
  height: 40px;
  margin-left: 20px;
  background-color: white;
  line-height: 40px;
  text-align: center;
}

.secondbuttonblack {
  cursor: pointer;
  border: none;
  border-radius: 25px;
  width: 112px;
  height: 40px;
  margin-left: 20px;
  background-color: black;
  line-height: 40px;
  text-align: center;
}

.firstwhite {
  font-size: 15px;
  text-decoration: underline;
  color: white;
}

.firstblack {
  font-size: 15px;
  text-decoration: underline;
  color: black
}

.secondwhite {
  font-size: 13px;
  font-weight: bold;
  color: black;
  /*background-color: white;*/
}

.secondblack {
  font-size: 13px;
  font-weight: bold;
  color: white;
  /*background-color: black;*/
}

.detailwhite {
  position: absolute;
  left: 23%;
  top: 610px;
  color: white;
  font-size: 40px;
  font-weight: bold;
  display: inline-block;
  height: 136px;
  width: 1000px;
  text-align: center;
  margin-top: 30px
}

.detailblack {
  position: absolute;
  left: 23%;
  top: 610px;
  color: black;
  font-size: 40px;
  font-weight: bold;
  display: inline-block;
  height: 136px;
  width: 1000px;
  text-align: center;
  margin-top: 30px
}

.headblack {
  position: absolute;
  left: 45%;
  top: 70px;
  font-size: 40px;
  font-weight: bold;
  color: black;
}

.headwhite {
  position: absolute;
  left: 45%;
  top: 70px;
  color: white;
  font-size: 40px;
  font-weight: bold
}

.homebottonwhite {
  cursor: pointer;
  margin-left: 30px;
  border: none;
  background-color: transparent;
  /*opacity: 0.1;*/
  color: white;
  font-size: 18px;
  font-weight: bold;
}

.homebottonblack {
  cursor: pointer;
  margin-left: 30px;
  border: none;
  background-color: transparent;
  /*opacity: 0.1;*/
  color: black;
  font-size: 18px;
  font-weight: bold;
}

/*.test1 {*/
/*  color: red;*/
/*  border: 2px solid red;*/
/*}*/
/*.test1 {*/
/*  color: red;*/
/*  border: 2px solid red;*/
/*}*/

.logo {
  /*position: absolute;*/
  left: 3%;
  color: black;
  font-size: 20px;
  /*border: 10px solid red;*/
  text-align: left;
  /*padding: 5px 5px 5px 10px;*/
}

.homeselectshite {
  cursor: pointer;
  text-decoration: underline;
  border: 2px dashed black;
  color: white;
  margin-left: 40px;
  background-color: transparent;
  font-size: 18px;
  font-weight: bold
}

.homeselect {
  cursor: pointer;
  text-decoration: underline;
  border: 2px dashed black;
  /*color: white;*/
  margin-left: 40px;
  background-color: transparent;
  font-size: 18px;
  font-weight: bold
}

.tvselect {
  cursor: pointer;
  text-decoration: underline;
  border: 2px dashed black;
  color: white;
  margin-left: 40px;
  background-color: transparent;
  font-size: 18px;
  font-weight: bold
}

.select {
  cursor: pointer;
  text-decoration: underline;
  border: 2px dotted black;
  color: black;
  margin-left: 35px;
  background-color: white;
  font-size: 18px;
  font-weight: bold;
}

.tvbotton {
  cursor: pointer;
  margin-left: 30px;
  border: none;
  background-color: transparent;
  /*opacity: 0.1;*/
  color: white;
  font-size: 18px;
}

.ico {
  /*position: relative;*/
  /*position: absolute;*/
  /*padding-left: 50px;*/
  /*position: absolute;*/
  /*left: 70%;*/
  /*padding-right: 10px;*/
  padding-left: 30px;
  /*text-align: right;*/
}

.tvprobutton {
  background-color: transparent;
  cursor: pointer;
  color: white;
  margin-left: 40px;
  border: none;
  font-size: 18px;
  font-weight: bold
}

.probutton {
  cursor: pointer;
  color: black;
  margin-left: 35px;
  border: none;
  background-color: white;
  font-size: 18px;
  font-weight: bold;
}

</style>
