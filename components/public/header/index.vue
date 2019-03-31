<template>
  <el-row class="m-header" :gutter="15">
    <el-col :span="6">
      <geo/>
    </el-col>
    <el-col :span="6">
      <div class="grid-content bg-purple"></div>
    </el-col>
    <el-col :span="6">
      <div class="grid-content bg-purple"></div>
    </el-col>
    <el-col :span="6">
      <div class="grid-content bg-purple"></div>
    </el-col>
  </el-row>
</template>

<script>
import Geo from "./geo.vue"
export default {
  data() {
    return {};
  },

  components: {
      Geo
  },

  computed: {},

  mounted: {},

  methods: {}
};
</script>
<style lang='scss' scoped>
</style>