<template lang="html">
    <Panel :class="$style.panel" title="精选推荐">
        <section :class="$style.content">
            <dl :class="$style.item" v-for="(item, index) in items" :key="index">
                <dt>{{ item.title }}<span>{{ item.sub }}</span></dt>
                <dd>{{ item.rate }}</dd>
                <dd>{{ item.text }}</dd>
            </dl>
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
            items: [{
                title: "定期理财",
                sub: "90天可质押",
                rate: "5.50%",
                text: "历史年化回报率",
            }, {
                title: "固收理财",
                sub: "理财首选",
                rate: "5.80%",
                text: "综合年化收益率",
            }, {
                title: "基智账户",
                sub: "组合投资",
                rate: "8%-10%",
                text: "止盈年化收益率",
            }, {
                title: "小白基金",
                sub: "天天赚钱",
                rate: "4.27%",
                text: "7日年化收益率",
            }],
        }
    },
}
</script>

<style lang="scss" module>
@import "../../css/element.scss";
.panel {
  @include panel;
  .content {
    @include flex(row);
    justify-content: space-around;
    box-sizing: border-box;
    &:after {
      content: " ";
      display: block;
      width: 100%;
      height: 1px;
      border: 1px solid #eee;
      position: relative;
      top: -208px;
      box-sizing: border-box;
    }
    .item {
      width: 50%;
      padding: 34px 16px;
      box-sizing: border-box;
      position: relative;
      &:nth-child(2n+1) {
        &:after {
          content: " ";
          width: 1px;
          height: 136px;
          border: 1px solid #eee;
          top: 50%;
          margin-top: -68px;
          position: absolute;
          right: 0px;
          display: block;
          box-sizing: border-box;
        }
      }
      dt {
        font-size: 30px;
        color: #333;
        line-height: 42px;
        span {
          font-size: 22px;
          color: #ff5155;
          border: 1px solid #ff5155;
          padding: 0 8px;
          margin-left: 10px;
          vertical-align: 1px;
        }
      }
      dd {
        &:nth-child(2) {
          font-weight: 700;
          font-size: 44px;
          height: 58px;
          line-height: 58px;
          color: #FF5155;
          white-space: nowrap;
          text-overflow: ellipsis;
          overflow: hidden;
        }
        &:nth-child(3) {
          font-size: 24px;
          height: 34px;
          line-height: 34px;
          color: #999;
          white-space: nowrap;
          text-overflow: ellipsis;
          overflow: hidden;
        }
      }
    }
  }
}
</style>
