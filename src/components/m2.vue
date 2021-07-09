<template>
  <div style="width: 100%;position: absolute;background-color: bisque;min-height: 670px;text-align: left;">
    <div style="width: 260px;border: 1px solid blue;float: left;margin-left: 200px">
      <h1><a href="#">手机/平板</a></h1>
      <div @mouseenter='sonshow' v-for='count in 6' :id='count' style="width: 260px;height: 55px;line-height: 55px"
           :key='"father"+count'>
        {{ count }}
        <i style="float: right;line-height: 55px" class="el-icon-arrow-right"></i>
      </div>
    </div>
    <div style="width: 560px;border: 1px solid blue;float: left;margin-left: 95px">
      <div v-show="son.s1" v-for='count in 10' :key="count"  style="width: 260px;height: 55px;float: top;">{{ count }}</div>
      <div v-show="son.s2" v-for='count in 14' :key="count"  style="width: 260px;height: 55px;float: top;">{{ count }}</div>
      <div v-show="son.s3" v-for='count in 9'  :key="count" style="width: 260px;height: 55px;float: top;">{{ count }}</div>
      <div v-show="son.s4" v-for='count in 8'  :key="count" style="width: 260px;height: 55px;float: top;">{{ count }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'm2',
  data () {
    return {
      son: {
        s1: true,
        s2: false,
        s3: false,
        s4: false
      }
    }
  },
  methods: {
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

</style>
