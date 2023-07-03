<template>
  <section class="board__columns__chart" >
    <div class="board__columns__chart__row title">
      {{ chartData.name }}
    </div>
    <div class="board__columns__chart__row userInfo">
      <div class="board__columns__chart__row userInfo assigne">
        {{ chartData.assigne }}
      </div>
      <div class="board__columns__chart__row userInfo points">
        {{ chartData.points }}
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "Chart",
  props: {
    chartData: Object,
  },
  data() {
    return {};
  },
  methods:{
    
  }
};
</script>

<style lang="scss" scoped>
.board__columns {
  &__chart {
    max-width: 90%;
    background: #f1f1f1;
    margin: 3px auto;
    border-radius: 7px;
    padding: 5px 3px;
    cursor: pointer;
    &:active {
        box-shadow: 1px 2px 3px #000;
      }
    &__row {
      
      &.title {
        font-weight: bold;
      }
      &.userInfo {
        &.points {
          background: #555;
          max-width: 20px;
          border-radius: 100%;
          text-align: center;
          color: #fff;
          width: 100%;
          height: 20px;
          display: flex;
          align-items: center;
          justify-content: center;
          font-size: 12px;
          margin: 0 auto;
          margin-right: 0px;
        }
      }
    }
  }
}
</style>
