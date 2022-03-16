<template>
  <div class="homebox">
    <mt-swipe :arto="4000">
      <mt-swipe-item v-for="item in swipeList" :key="item.id">
        <img :src="item.img_url" alt="" />
      </mt-swipe-item>
    </mt-swipe>
    <ul class="mui-table-view mui-grid-view mui-grid-9">
      <li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-4">
        <router-link to="/home/newslist" href="#">
          <span class="mui-icon mui-icon-home"></span>
          <div class="mui-media-body">校园新闻</div></router-link
        >
      </li>
      <li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-4">
        <router-link to="/home/imagelist" href='#'>
          <span class="mui-icon mui-icon-extra mui-icon-extra-heart"><span class="mui-badge"></span></span>
          <div class="mui-media-body">校园风景</div></router-link>
        
      </li>
      <li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-4">
        <router-link to="/home/goodslist" href='#'>
          <span class="mui-icon mui-icon-extra mui-icon-extra-cart"></span>
          <div class="mui-media-body">易购商城</div></router-link>
      </li>
      <li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-4">
        <a href="#">
          <span class="mui-icon mui-icon-location"></span>
          <div class="mui-media-body">位置签到</div></a
        >
      </li>
      <li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-4">
        <a href="#">
          <span class="mui-icon mui-icon-search"></span>
          <div class="mui-media-body">搜索</div></a
        >
      </li>
      <li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-4">
        <a href="#">
          <span class="mui-icon mui-icon-phone"></span>
          <div class="mui-media-body">老师通讯录</div></a
        >
      </li>
      <li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-4">
        <a href="#">
          <span class="mui-icon mui-icon-gear"></span>
          <div class="mui-media-body">设置</div></a
        >
      </li>
      <li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-">
        <a href="#">
          <span class="mui-icon mui-icon-info"></span>
          <div class="mui-media-body">问题反馈</div></a
        >
      </li>
      <li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-4">
        <a href="#">
          <span class="mui-icon mui-icon-more"></span>
          <div class="mui-media-body">更多</div></a
        >
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  data() {
    return {
      swipeList: [],
    };
  },
  created() {
    this.getSwipeData();
  },
  methods: {
    getSwipeData() {
      this.$http.get("http://www.barteam.cn:8086/sliderlist").then((res) => {
        console.log(res.data.Data);
        this.swipeList = res.data.Data;
      });
    },
  },
};
</script>
<style lang="less">
.homebox {
  .mint-swipe {
    width: 100%;
    height: 260px;
    img {
      width: 100%;
    }}
    //九宫格样式
    .mui-grid-view{
      padding-bottom: 50px;
    }
  
}
</style>