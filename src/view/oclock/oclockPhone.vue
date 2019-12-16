<template>
  <div style="margin-top:80px;"
       @click="clickPhoneHandle">
    <oneOclock v-if="oVif" />
  </div>
</template>

<script>
import oneOclock from './components/oneOclock'
export default {
  name: 'oclock',
  props: {},
  components: {
    oneOclock
  },
  data () {
    return {
      oVif: true
    }
  },
  computed: {},
  methods: {
    clickPhoneHandle () {
      this.oVif = false
      this.$nextTick(() => {
        this.oVif = true
      })
    }
  },
  created () { },
  activated () { },
  mounted () {
  },
  beforeDestroy () { }
}
</script>

<style lang="less">
</style>
