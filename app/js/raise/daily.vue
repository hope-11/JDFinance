<template lang="html">
    <Panel :class="$style.panel" title="每日签到">
        <section :class="$style.content">
            <img src="//img12.360buyimg.com/jrpmobile/jfs/t3184/283/6032981290/37056/fa30c674/589bd5a2Nabdbbbd9.jpg" alt="">
            <img src="//img12.360buyimg.com/jrpmobile/jfs/t3298/196/6130416421/33755/a0536d3e/589bd5d4Nf32e7adc.jpg" alt="">
            <p>不抢白不抢</p>
        </section>
    </Panel>
</template>

<script>
import Panel from "../core/panel.vue"
export default {
    components: {
        Panel,
    },
}
</script>

<style lang="scss" module>
@import "../../css/element.scss";
.panel {
  @include panel;
  margin-top: 0!important;
  .content {
    padding-bottom: 40px;
    position: relative;
    @include flex(row);
    img {
      width: 50%;
      height: 100%;
    }
    p {
      position: absolute;
      top: -112px;
      right: 32px;
      font-size: 28px;
      color: #999;
      line-height: 112px;
    }
  }
}
</style>
