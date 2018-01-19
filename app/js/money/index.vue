<template lang="html">
    <div>
        <Heador/>
        <Slider/>
        <Coupon/>
        <Recommend/>
        <Ad2/>
        <Finance/>
        <ad3/>
        <Footor cname="mfooter"/>
        <Navbar/>
    </div>
</template>

<script>
import Heador from "../public/header.vue"
import Footor from "../public/footer.vue"
import Navbar from "../public/navbar.vue"
import Slider from "./mslider.vue"
import Coupon from "./coupon.vue"
import Recommend from "./recommend.vue"
import Ad2 from "./ad2.vue"
import Finance from "./finance.vue"
import Ad3 from "./ad3.vue"
export default {
    components: {
        Heador,
        Footor,
        Navbar,
        Slider,
        Coupon,
        Recommend,
        Ad2,
        Finance,
        Ad3,
    },
}
</script>

<style lang="scss">
  .mfooter {
    ul {
      >li {
        display: none;
      }
    }
  }
</style>
