<template>
  <div @mouseleave="mslog"
       style="width: 100%;position: absolute;background-color: white;min-height: 695px;text-align: left;">
    <div style="margin-top: 45px;width: 260px;float: left;margin-left: 200px">
      <h1><a href="#" style="color: black">手机/平板</a></h1>
      <div @mouseenter='sonshow($event),fatherselect($event)' v-for='(item,index) in m1list' :id='index+1'
           style="width: 260px;height: 55px;line-height: 55px;color: black;font-size: 18px"
           :key='"father"+index'>
        {{ item }}
        <i  style="float: right;line-height: 55px;display: none" class="el-icon-arrow-right"></i>
      </div>
    </div>
    <div id="m1son" style="margin-top: 135px;width: 560px;float: left;margin-left: 95px">
      <div v-show="son.s1" v-for='item in son1list' :key="item" style="width: 260px;height: 55px;float: top;"><a
        href='#' style="position: relative">{{ item }}</a>
      </div>
      <div v-show="son.s2" v-for='item in son2list' :key="item" style="width: 260px;height: 55px;float: top;"><a
        href='#' style="position: relative">{{ item }}</a>
      </div>
      <div v-show="son.s3" v-for='item in son3list' :key="item" style="width: 260px;height: 55px;float: top;"><a
        href='#' style="position: relative">{{ item }}</a>
      </div>
      <div v-show="son.s4" v-for='item in son4list' :key="item" style="width: 260px;height: 55px;float: top;"><a
        href='#' style="position: relative">{{ item }}</a>
      </div>
      <div v-show="son.s5" v-for='item in son5list' :key="item" style="width: 260px;height: 55px;float: top;"><a
        href='#' style="position: relative">{{ item }}</a>
      </div>
      <div v-show="son.s6" v-for='item in son6list' :key="item" style="width: 260px;height: 55px;float: top;"><a
        href='#' style="position: relative">{{ item }}</a>
      </div>
      <div v-show="son.s7" v-for='item in son7list' :key="item" style="width: 260px;height: 55px;float: top;">
        <a href='#' style="position: relative">{{ item }}</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'm1',
  data () {
    return {
      m1list: [
        '新品推荐',
        '智能手机',
        '智能平板',
        '智能手表',
        'Samsung Galaxy Buds',
        '智能产品配件',
        '应用&服务',
        'Why Galaxy',
        '三星Galaxy 授权体验店'
      ],
      son1list: [
        'Galaxy 5G',
        'Galaxy S21 Ultra 5G',
        'GalaxyS21 | S21+ 5G',
        'GalaxyS20 FE 5G',
        'Galaxy Z Fold25G',
        'Galaxy Z Flip 5G .',
        '三星W21 5G',
        'Galaxy A52 5G',
        'Galaxy F52 5G',
        'Samsung Galaxy Buds Pro'
      ],
      son2list: [
        '全系列产品',
        'Galaxy Z',
        'GalaxyS',
        'Galaxy Note',
        'Galaxy A',
        'Galaxy F',
        'Samsung Galaxy M',
        '三星W',
        '智能手机配件',
        '查看:全部'
      ],
      son3list: [
        '全系列产品',
        'Galaxy Tab S',
        'Galaxy Tab A',
        '智能平板配件',
        '查看全部'
      ],
      son4list: [
        '全系列产品',
        'Samsung Galaxy Watch',
        'Samsung Galaxy Watch Active',
        '智能手表配件',
        '查看全部'
      ],
      son5list: [
        '全系列产品',
        'Samsung Galaxy Buds',
        'AKG耳机'
      ],
      son6list: [
        '全系列产品',
        '智能手机配件',
        '智能平板配件',
        '智能穿戴设备配件',
        '查看全部'
      ],
      son7list: [
        '全系列产品.',
        '三星应用商店',
        '三星游戏中心',
        'Bixby',
        'Samsung Pay',
        '三星健康',
        'Samsung DeX',
        '盖乐世社区',
        'Samsung',
        'One UI',
        '三星畅联',
        'S换机助手',
        '查看全部'
      ],
      son: {
        s1: false,
        s2: false,
        s3: false,
        s4: false,
        s5: false,
        s6: false,
        s7: false

      }
    }
  },
  methods: {
    fatherselect: function (e) {
      // console.log(e.target.children)
      var fatherlength = e.target.parentNode.children.length
      // console.log(typeof fatherlength)
      // e.target.style.fontWeight = 'bolder'
      // console.log(e.target.parentNode.children[1].style.fontWeight = 'bolder')
      // console.log(e.target.parentNode.children[0].style.fontWeight = 'bolder')
      for (var i = 1; i < fatherlength; i++) {
        e.target.parentNode.children[i].style.fontWeight = 'normal'
        e.target.parentNode.children[i].children[0].style.display = 'none'
        // console.log(e.target.parentNode.children[i].style.fontWeight)
      }
      e.target.style.fontWeight = 'bolder'
      e.target.children[0].style.display = 'block'
    },
    mslog: function (e) {
      this.$emit('listleave', e)
      // console.log(1)
    },
    sonshow: function (e) {
      for (const key in this.son) {
        this.son[key] = false
      }
      var objkey = 's' + e.target.id
      this.son[objkey] = true
    }
  }
}
</script>

<style scoped>
#m1son div a:after{
  content: '';
  /*top: auto;*/
  /*left: auto;*/
  width: 0;
}
/*#m1son div a:before{*/
/*  content: '';*/
/*  !*top: auto;*!*/
/*  !*left: auto;*!*/
/*  width: 0;*/
/*}*/
/*#m1son div a:hover:before{*/
/*  font-weight: bolder;*/
/*  content: '';*/
/*  position: absolute;*/
/*  bottom: -3px;*/
/*  !*top: auto;*!*/
/*  left: 0px;*/
/*  !*left: auto;*!*/
/*  height: 1px;*/
/*  width: 100%;*/
/*  background-color: #E4262D;*/
/*  transition: width 1s ease;*/
/*  !*text-decoration: underline;*!*/
/*  !*border-bottom: 1px solid black;*!*/
/*  !*border-bottom-width: 10px;*!*/
/*  !*transition: border-bottom-width  1s ease;*!*/
/*}*/
#m1son div a:hover{
  font-weight: bolder;
  /*transition: all 0.4s linear;*/
}
#m1son div a:hover:after{
  /*font-weight: bolder;*/
  content: '';
  position: absolute;
  bottom: -3px;
  /*top: auto;*/
  left: 0%;
  /*left: auto;*/
  height: 1px;
  width: 100%;
  transform: rotateY(180deg);
  background-color: black;
  transition: transform 0.3s linear;
  /*text-decoration: underline;*/
  /*border-bottom: 1px solid black;*/
  /*border-bottom-width: 10px;*/
  /*transition: border-bottom-width  1s ease;*/
}
div a {
  color: black;
  text-decoration: none;
}

</style>
