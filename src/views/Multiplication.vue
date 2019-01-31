<template>
  <div class="warp">
    <div class="container">
      <div class="titleBlock">
        <h1 class="title">九九乘法表</h1>
        <span class="sub_title">MULTIPLICATION CHART</span>
        <span class="cross-rightUp">×</span>
        <span class="cross-rightDowm">×</span>
        <span class="cross-leftUp">×</span>
        <span class="cross-leftDowm">×</span>
      </div>
        <MultipcationTable v-for="item in blockNumberArray" :key="item.blockNumber"
        :number="item"></MultipcationTable>
    </div>
    <footer>
      <p class="lisence">Copyright © 2019 HexSchool. All rights reserved.</p>
    </footer>
  </div>
</template>

<script>
// @ is an alias to /src
import MultipcationTable from '@/components/multipcationTable.vue';

export default {
  name: 'multiplication',
  components: {
    MultipcationTable,
  },
  data() {
    return {
      blockNumber: 8,
    };
  },
  computed: {
    blockNumberArray() {
      const vm = this;
      const arr = [];
      for (let i = 1; i <= vm.blockNumber; i += 1) {
        arr.push(i + 1);
      }
      return arr;
    },
  },
};
</script>

<style scoped lang="scss">
  .warp {
    width: 1280px;
    margin: 0 auto;
    background: #F0F0F0;
  }
  .container {
    padding-left: 85px;
    padding-right: 85px;
    padding-top: 80px;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
  }
  .titleBlock{
    width: 350px;
    color:#2EB738;
    position: relative;
    margin-bottom: 40px;
    padding-left: 35px;
    padding-right: 35px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    &:before{
      content: "";
      position: absolute;
      height: 1px;
      background: #2EB738;
      top: 12px;
      right: 0;
      left: 0;
      margin-right: 35px;
      margin-left: 35px;
    }
    &:after{
      content: "";
      position: absolute;
      height: 1px;
      background: #2EB738;
      bottom: 12px;
      right: 0;
      left: 0;
      margin-right: 35px;
      margin-left: 35px;
    }
  }
  .title{
    font-size: 56px;
    padding-top: 11px;
    padding-bottom: 11px;
    font-family: 'Noto Sans TC';
  }
  .sub_title{
    display: block;
    text-align: center;
    font-size: 24px;
    white-space: nowrap;
    font-family: 'Noto Sans TC';
  }
  .cross-rightUp,.cross-rightDowm,.cross-leftUp,.cross-leftDowm{
      position: absolute;
      font-size: 24px;
  }
  .cross-rightUp{
    top: 0;
    right: 0;
  }
  .cross-rightDowm{
    bottom: 0;
    right: 0;
  }
  .cross-leftUp{
    top: 0;
    left: 0;
  }
  .cross-leftDowm{
    bottom: 0;
    left: 0;
  }
  footer {
    background: #2EB738;
    text-align: right;
    .lisence{
      padding-top: 8px;
      padding-bottom: 8px;
      padding-right: 85px;
      font-size: 16px;
      color: white;
      font-family: 'Noto Sans TC', sans-serif;
    }
  }
</style>
