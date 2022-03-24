<template>
  <div>
    <HeadTop head-title="电影列表" go-back="true"></HeadTop>
    <detail></detail>

    <div class="contain">
      
      <van-tabs v-model="active" scrollspy sticky>
        <van-tab v-for="value in banner_list" :key="value" :title="value">
        </van-tab>

          <intro></intro>
          <recomm></recomm>
           <discuss></discuss>
      
      </van-tabs>
    </div>
    
  </div>
</template>

<script>
import HeadTop from "@/components/header/Head";
import detail from "./intro/detail";
import recomm from "./intro/recommend";
import discuss from "./intro/discuss";
import intro from "./intro/intro";
export default {
  name: "movie",
  data() {
    return {
      banner_list:['简介','推荐','影评']
    };
  },
  components: { HeadTop, detail,discuss,recomm,intro},
};
</script>

<style lang="scss" >
.contain {
  background-color: white;
}
</style>