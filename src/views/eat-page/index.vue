<template>
  <div class="eatPage">
    今天吃了么
    <History />
  </div>
</template>

<script>
import History from './history.vue'
export default {
  components: {
    History
  },
  props: {},
  data() {
    return {}
  },
  mounted() {},
  methods: {}
}
</script>
<style lang="scss" scoped>
.eatPage {
  height: calc(100vh - 80px);
  margin: 10px;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}
</style>
