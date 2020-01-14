<template>
  <div>
    <h3 style="clear:both;">姓名：彭乐棠 日期：_______________</h3>
    <h3 style="clear:both;">4道竖式题</h3>
    <div v-for="c in 4" :key="'shushi' + c" style="width:150px; height:300px; float:left; text-align:left;">
      <kousuan :minNum="3" :maxNum="70" shushi />
    </div>
    <h3 style="clear:both;">30道口算题</h3>
    <div v-for="c in 30" :key="c" style="width:200px; height:50px; float:left; text-align:left;">
      <kousuan :minNum="3" :maxNum="28" />
    </div>
  </div>
</template>

<script>
import kousuan from './components/kousuan'
export default {
  name: 'GradeTwoMath',
  props: {},
  components: {
    kousuan
  },
  data () {
    return {
    }
  },
  watch: {},
  computed: {},
  methods: {},
  filters: {},
  created () { },
  activated () { },
  mounted () { },
  beforeDestroy () { }
}
</script>

<style lang="less">
</style>
