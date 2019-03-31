<template>
  <div class="page-index">
    <el-row>
      <el-col :span="5"><emenu/></el-col>
      <el-col :span="19"><life/></el-col>
    </el-row>
    <el-row>
      <el-col :span="24">3</el-col>
    </el-row>
    <div style="width:200px;height:200px;background:red;position:relative;top:-200px;"></div>
  </div>
</template>

<script>
import Emenu from "@/components/index/menu.vue"
import Life from '@/components/index/life.vue'
export default {
  components:{
    Emenu,
    Life
  }
};
</script>
<style lang="scss">
  @import "@/assets/css/index/index.scss";
</style>
