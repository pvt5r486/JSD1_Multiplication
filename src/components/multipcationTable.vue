<template>
  <div class="card" v-html="outPut">
  </div>
</template>

<script>
export default {
  name: 'multipcationTable',
  props: {
    number: {
      type: Number,
      default: 1,
    },
  },
  computed: {
    outPut() {
      const vm = this;
      let part1 = '';
      let part2 = '';
      for (let i = 1; i < 10; i += 1) {
        if (i <= 3) {
          part1 = `${part1}<li>${vm.number} × ${i} ＝ ${vm.number * i}</li>`;
        } else {
          part2 = `${part2}<li>${vm.number} × ${i} ＝ ${vm.number * i}</li>`;
        }
      }
      const HtmlStr = `
        <div>
          <h2 class="card_title">${vm.number}</h2>
          <ul class="calc">${part1}</ul>
        </div>
        <div class="second_side">
          <ul class="calc">${part2}</ul>
        </div>`;
      return HtmlStr;
    },
  },
};
</script>

<style lang="scss">
  .card {
    width: 350px;
    padding: 64px 40px 64px 40px;
    color:#2EB738;
    margin-bottom: 40px;
    background: #FFFFFF;
    font-family: 'Noto Sans TC', sans-serif;
    display: flex;
    overflow: hidden;
    border-radius: 100px 0px 30px 0px;
    box-shadow: 0px 3px 10px #D8D8D8;
    &:nth-child(2),&:nth-child(5),&:nth-child(8){
      margin-right: 30px;
      margin-left: 30px;
    }
  }
  .card_title{
    font-size: 128px;
    font-weight: bolder;
    text-align: center;
    text-shadow: 4px 3px 0 #F0F0F0;
  }
  .calc{
    font-size: 24px;
    li{
      margin-bottom: 8px;
      line-height: 33px;
      &:last-child{
        margin-bottom: 0px;
      }
    }
  }
  .second_side{
    margin-left: auto;
    margin-top: 4px;
  }
</style>
