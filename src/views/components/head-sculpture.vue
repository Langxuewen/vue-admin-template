<template>
  <div class="wrap">
    <img class="img" :src="require('@/assets/' + url)" alt="加载失败">
    <div class="name">{{ name }}</div>
  </div>
</template>

<script>

export default {
  components: {},
  props: {
    url: {
      type: String,
      default: ''
    },
    name: {
      type: String,
      default: ''
    }
  },
  data() {
    return {
    }
  },
  computed: {
  },
  mounted() {},
  methods: {}
}
</script>
<style lang="scss" scoped>
.wrap {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  text-align: center;
  .img {
    height: 60px;
    width: 60px;
    display: inline-block;
  }
  .name {
    font-weight: 600;
    color: #788595;
    margin-top: 5px;
  }
}
</style>
