<template>
  <div style="font-size:18px;">
    {{result}}
  </div>
</template>

<script>
export default {
  name: 'kousuan',
  props: {
    shushi: {
      type: Boolean,
      default: false
    },
    minNum:{
      type: Number,
      default: 1
    },
    maxNum: {
      type: Number,
      default: 30
    }
  },
  components: {},
  data () {
    return {
      result: ''
    }
  },
  watch: {},
  computed: {},
  methods: {
    AtimesBminusC () {
      const a = this.raNum(2,9)
      const b = this.raNum(2,9)
      const c = this.raNum(2,a*b)
      return `${a} × ${b} - ${c} =`
    },
    AtimesBplusC () {
      const a = this.raNum(2,9)
      const b = this.raNum(2,9)
      const c = this.ra()
      return `${a} × ${b} + ${c} =`
    },
    AtimesB () {
      const a = this.raNum(2,9)
      const b = this.raNum(2,9)
      return `${a} × ${b} =`
    },
    AminusBplusC () {
      const r = this.ra() + 10
      const a = this.raNum(3,r-1)
      const b = this.ra()
      return `${r} - ${a} + ${b} =`
    },
    AplusBminusC () {
      const a = this.ra()
      const b = this.ra()
      const c = this.raNum(1,a+b-1)
      return `${a} + ${b} - ${c} =`
    },
    AminusBminusC () {
      const r = this.ra() + 10
      const a = this.raNum(3,r-1)
      const b = this.raNum(1,r-a-1)
      return `${r} - ${a} - ${b} =`
    },
    AminusB () {
      const r = this.ra() + 3
      const a = this.raNum(1,r-1)
      return `${r} - ${a} =`
    },
    AplusBplusC () {
      const a = this.ra()
      const b = this.ra()
      const c = this.ra()
      return `${a} + ${b} + ${c} =`
    },
    AplusB (){
      const a = this.ra()
      const b = this.ra()
      return `${a} + ${b} =`
    },
    ra () {
      return this.raNum(this.minNum,this.maxNum)
    },
    // 几到几的随机数
    raNum (b,e) {
      e = e - b+1;
      if(!b && b!=0 || !e){return "?";}   
      return Math.floor( ( Math.random() * e ) + b );  
    },
    getShushi () {
      const s = this.raNum(1,6)
      let r = ''
      if (s === 1)
      r = this.AplusB()
      if (s === 2)
      r = this.AminusB()
      if (s === 3)
      r = this.AplusBplusC()
      if (s === 4)
      r = this.AplusBminusC()
      if (s === 5)
      r = this.AminusBminusC()
      if (s === 6)
      r = this.AminusBplusC()
      this.result = r
    },
    getNormal () {
      const s = this.raNum(1,9)
      // console.info('s', s)
      let r = ''
      if (s === 1)
      r = this.AplusB()
      if (s === 2)
      r = this.AminusB()
      if (s === 3)
      r = this.AtimesB()
      if (s === 4)
      r = this.AplusBplusC()
      if (s === 5)
      r = this.AminusBminusC()
      if (s === 6)
      r = this.AminusBplusC()
      if (s === 7)
      r = this.AtimesBplusC()
      if (s === 8)
      r = this.AtimesBminusC()
      if (s === 9)
      r = this.AplusBminusC()
      this.result = r
    },
  },
  filters: {},
  created () {
    if(this.shushi) {
      this.getShushi()
    } else {
      this.getNormal()
    }

  },
  activated () { },
  mounted () { },
  beforeDestroy () { }
}
</script>

<style lang="less">
</style>
