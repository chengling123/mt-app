<template>
  <div class="search-panel">
    <el-row class="m-header-searchbar">
      <el-col
        :span="3"
        class="left">
        <img
          src="//s0.meituan.net/bs/fe-web-meituan/e5eeaef/img/logo.png"
          alt="美团">
      </el-col>
      <el-col
        :span="15"
        class="center">
        <div class="wrapper">
          <el-input
            @input="input"
            @focus="focus"
            @blur="blur"
            v-model="search"
            placeholder="搜索商家或地点"
           />
          <button class="el-button el-button--primary"><i class="el-icon-search"/></button>
          <dl class="hotPlace" v-if="isHotPlace">
            <dt>热门搜索</dt>
            <dd v-for="(item,index) in hotPlace" :key="index">{{item}}</dd>
          </dl>
          <dl class="searchList" v-if="isSearchList">
            <dd v-for="(item,index) in searchPlace" :key="index">{{item}}</dd>
  
          </dl>
        </div>
        <p class="suggest">
          <a href="#">故宫博物院</a>
          <a href="#">故宫博物院</a>
          <a href="#">故宫博物院</a>
          <a href="#">故宫博物院</a>
          <a href="#">故宫博物院</a>
        </p>
        <ul class="nav">
          <li><nuxt-link
            to="/"
            class="takeout">美团外卖</nuxt-link></li>
          <li><nuxt-link
            to="/"
            class="movie">猫眼电影</nuxt-link></li>
          <li><nuxt-link
            to="/"
            class="hotel">美团酒店</nuxt-link></li>
          <li><nuxt-link
            to="/"
            class="apartment">民宿/公寓</nuxt-link></li>
          <li><nuxt-link
            to="/"
            class="business">商家入驻</nuxt-link></li>
        </ul>
      </el-col>
      <el-col
        :span="6"
        class="right">
        <ul class="security">
          <li><i class="refund"/><p class="txt">随时退</p></li>
          <li><i class="single"/><p class="txt">不满意免单</p></li>
          <li><i class="overdue"/><p class="txt">过期退</p></li>
        </ul>
      </el-col>
    </el-row>
  </div>
</template>

<script>
export default {
  data(){
    return{
      isFocus:false,
      search:"",
      hotPlace:["火锅","西餐","湘菜"],
      searchPlace:["海鲜","川菜","杭帮菜"],
    }
  },
  computed:{
    isHotPlace:function(){
      // 想让热门推荐有效，满足2个条件 1.聚焦状态 2.热门搜索为空，
      return this.isFocus&&!this.search
    },
    isSearchList:function(){
      return this.isFocus&&this.search
    }
  },
  methods:{
    focus(){
      this.isFocus=true
    },
    blur(){
      // 因为鼠标点击链接时，会先触发blur事件则我还没点击到链接，面板就被收起来了，导致我们的点击没有生效，所以我们需要延迟执行blur事件
      setTimeout(()=>{
        this.isFocus=false
      },200)
    },
    input(){
    }
  }
}
</script>

<style lang="css">
</style>
