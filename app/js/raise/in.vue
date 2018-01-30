<template lang="html">
    <Panel :class="$style.panel" title="In货推荐">
        <section :class="$style.content">
            <div :class="$style.item" v-for="(item, index) in items" :key="index">
                <img :src="item.category" alt="">
                <section :class="$style.list">
                    <div :class="$style.product" v-for="(product, index) in item.list" :key="index">
                        <img :src="product.img" alt="">
                        <p :class="$style.title">{{ product.title }}</p>
                        <p :class="$style.price"><em>{{ product.price }}</em>起</p>
                        <article>
                            <div :class="$style.wrapper">
                                <div :class="$style.inner" :style="{width: product.progress + '%'}"/>
                            </div>
                            <p>{{ product.progress }}%</p>
                        </article>
                        <label v-if="product.well">精选</label>
                    </div>
                </section>
            </div>
        </section>
    </Panel>
</template>

<script>
import Panel from "../core/panel.vue"
export default {
    components: {
        Panel,
    },
    data() {
        return {
            items: [
                {
                    category: "//img12.360buyimg.com/jrpmobile/jfs/t3406/210/2247820735/50952/86016eea/5846d8e7N20446dbd.png?width=750&height=200",
                    list: [
                        {
                            img: "//img30.360buyimg.com/cf/s250x250_jfs/t16150/165/674827881/130789/7de1f069/5a3a04b0N4e3d246c.jpg",
                            title: "骨传导耳机",
                            price: "19.00",
                            progress: 381,
                            well: true,
                        },
                        {
                            img: "//img30.360buyimg.com/cf/s250x250_jfs/t15514/150/953212838/145464/850c2d0f/5a448bc7Nade1a7c5.jpg",
                            title: "未来游戏装备",
                            price: "159.00",
                            progress: 999,
                        },
                    ],
                },
                {
                    category: "//img12.360buyimg.com/jrpmobile/jfs/t3739/82/2244582797/54399/746c7d79/5846a953N66b67d05.png?width=750&height=200",
                    list: [
                        {
                            img: "//img30.360buyimg.com/cf/s250x250_jfs/t14881/283/656508232/143980/9b606acf/5a33a171N18c9c80a.jpg",
                            title: "蓝牙音箱",
                            price: "29.00",
                            progress: 60,
                        },
                        {
                            img: "//img30.360buyimg.com/cf/s250x250_jfs/t14767/339/1285461444/50279/8ee27acb/5a4c3a82N3cff563e.jpg",
                            title: "全球漫游WiFi卡",
                            price: "65.00",
                            progress: 274,
                        },
                    ],
                },
                {
                    category: "//img12.360buyimg.com/jrpmobile/jfs/t3214/113/4408032436/61548/ce316eef/5846d310Ne93f00c9.png?width=750&height=200",
                    list: [
                        {
                            img: "//img30.360buyimg.com/cf/s250x250_jfs/t8245/192/196081959/46158/74227a9a/59a26d4bNddd40149.jpg",
                            title: "遵义虾子土豆片",
                            price: "1.00",
                            progress: 0,
                        },
                        {
                            img: "//img30.360buyimg.com/cf/s250x250_jfs/t10993/26/1955036662/116896/13538743/59ec19ecN5efa5c7d.jpg",
                            title: "新疆黄杏干",
                            price: "35.00",
                            progress: 0,
                        },
                    ],
                },
            ],
        }
    },
}
</script>

<style lang="scss" module>
@import "../../css/element.scss";
.panel {
  @include panel;
  .content {
    @include flex;
    .item {
      margin-bottom: 40px;
      >img {
        display: block;
        width: 100%;
      }
      .list {
        @include flex(row);
        .product {
          width: 50%;
          height: 396px;
          box-sizing: border-box;
          background: rgba(0,0,0,.02);
          text-align: center;
          position: relative;
          img {
            width: 180px;
            height: 180px;
            margin: 44px auto 20px;
          }
          .title {
            font-family: PingFangSC-Medium;
            font-size: 28px;
            color: #444;
          }
          .price {
            font-family: PingFangSC-Semibold;
            font-size: 20px;
            color: #999;
            line-height: 48px;
            em {
              font-size: 36px;
              color: #ff3232;
              margin-right: 4px;
              &:before {
                content: "￥";
                font-size: 28px;
              }
            }
          }
          article {
            @include flex(row);
            align-items: center;
            justify-content: space-around;
            padding: 0 20px;
            line-height: 30px;
            margin-top: 16px;
            .wrapper {
              width: 144px;
              height: 10px;
              background: #F6E6E6;
              border-radius: 22px;
              .inner {
                width: 40%;
                max-width: 100%;
                height: 10px;
                background-image: linear-gradient(270deg,#F55 1%,#FF9C31 100%);
                border-radius: 22px;
              }
            }
            p {
              font-size: 24px;
              color: #999;
            }
          }
          label {
            position: absolute;
            left: 0;
            top: 0;
            font-family: PingFangSC-Medium;
            font-size: 20px;
            color: #FF0000;
            text-align: center;
            padding: 4px 8px;
            background-image: linear-gradient(-35deg,#C1C1C1 0,#ACACAC 100%);
          }
        }
      }
    }
  }
}
</style>
