<template>
  <div class="vux-flexbox" :class="{'flex-col': orient === 'vertical', 'flex-row': orient === 'horizontal'}">
    <slot></slot>
  </div>
</template>

<script>
export default {
  props: {
    gutter: {
      type: Number,
      default: 8
    },
    orient: {
      type: String,
      default: 'horizontal'
    }
  }
}
</script>

<style lang="less">
.vux-flexbox{
  width: 100%;
  text-align: left;
  display: flex;
  box-align: center;
  align-items: center;
}
.vux-flexbox .vux-flexbox-item {
  flex: 1;
  min-width: 20px;
}
.vux-flexbox-item > .vux-flexbox {
  width: 100%;
}

.vux-flexbox .vux-flexbox-item:first-child{
  margin-left: 0!important;
  margin-top: 0!important;
}
.flex-col {
  box-orient: vertical;
  flex-direction: column;
}
.flex-col > .vux-flexbox-item {
  width: 100%;
}
.flex-row {
  box-direction: row;
  box-orient: horizontal;
  flex-direction: row;
}
</style>
