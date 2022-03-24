<template>
  <div class="detail">
    <van-row class="top">
      <van-col span="8" class="movie_img">
        <img src="" alt="" />
        <span>
          {{ like }}喜欢       
          </span>
      </van-col>

    
      <van-col span="16" class="left">
        <h1>
          <strong>唐人街探案3唐人街探案3       
          </strong>
        </h1>
        <ul>
          <li>xx分钟 / 喜剧 / 中国 日本</li>
          <li>2020-xx-xx xx地区上映</li>
          <li>
            推评分 xx分
            <mark style="background-color: #0000; color: orange">
              （xx人评分)
            </mark>
          </li>
        </ul>
      </van-col>


    </van-row>

    
      <div class="action van-hairline--surround">
        <span> 
          <van-icon  :style="colorChange" @click="isLike()" name="like" />
          喜欢</span>
        <span>
          <van-icon  name="comment" /> 
           评论
          </span>
        <span> 
          <van-icon  name="share" />
           分享
          </span>
      </div>
   
  </div>

</template>

<script>
export default {
  
  data() {
    return {
      like: 0,
      colorChange:{}
    };
  },
  methods:{
    isLike(){
      if(!this.like){
      this.like++  
      this.colorChange={
         color:'orange'
      }
      }
      else{
        this.like--
        this.colorChange={}
      }
    }
  }
};
</script>

<style lang="scss" scoped>
$size:.26rem;
$light-gray:#b1b1b1;
i{
  color:gray
}
.detail {
  width:100%;
  background-color: white;
  margin: 0 auto;
  padding: $size*1.5 $size*2 0 $size*2;
  margin-bottom: 0.39rem;
  font-size: 0.27rem;
  display: -webkit-flex;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  .top {

    height: 3.5rem;
    width: 84%;
    .movie_img {
      background-color: grey;
      height: 100%;
      position: relative;
      span {
        position: absolute;
        display: block;
        width: 100%;
        height: 24%;
        background-color: black;
        opacity: 0.5;
        bottom: 0;
        color: white;
        text-align: right;      
        margin: auto 0;
        padding: 7px;
      }
    }
    .left {
      height: 100%;
      padding-left:$size;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      li {
       color: $light-gray;
       word-spacing: 4px;
       margin-top: 5px;
      }
    }
  }
  [class*="van-hairline"]::after{
 border: none;
  }
  .action {
   
    width: 90%;
    text-align: center;
    margin: $size 0;
    display: flex;
    justify-content: space-around; 
    box-shadow: 0 3px 8px 0 $light-gray;
    border-radius: 5px;
     span{
      font-size: $size*1.3;
      padding:$size*0.85 0;
     }
  }
}
</style>