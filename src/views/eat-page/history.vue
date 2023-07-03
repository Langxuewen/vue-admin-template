<template>
  <div class="history">
    <div class="title">历史记录</div>
    <div class="head-sculpture">
      <HeadSculpture url="images/head-sculpture/boy.png" name="小夫" />
      <HeadSculpture url="images/head-sculpture/girl.png" name="梦祎" />
    </div>
  </div>
</template>

<script>
import HeadSculpture from '../components/head-sculpture.vue'
export default {
  components: { HeadSculpture },
  props: {},
  data() {
    return {}
  },
  mounted() {},
  methods: {}
}
</script>
<style lang="scss" scoped>
.history {
  width: 400px;
  max-height: 100%;
  border: 1px solid #eee;
  overflow-y: auto;
  .title {
    text-align: center;
    padding: 15px;
    font-size: 20px;
    font-weight: 600;
  }
  .head-sculpture {
    display: flex;
    flex-direction: row;
    justify-content: space-around;
  }
}
</style>
