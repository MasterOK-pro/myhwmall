<template>
  <div class="classify">
    <!-- <div class="test" @click="toProduct">classify</div> -->
    <!-- app首页底部导航按钮 -->
    <div class="wrap">
      <div class="header iconfont">
        <div class="search" @click="$router.push('search')">
          <a href class="da3">
            <img src="../assets/images/da3.png" alt />
          </a>
          <input type="text" placeholder="P40 pro" disabled />
        </div>
        <div class="icon">
          <a href>
            <img src="../assets/images/liao.png" alt />
          </a>
        </div>
      </div>
      <div class="main">
        <div class="left">
          <ul class="list">
            <li v-for="(item,index) in dataList" :key="index">
              <span :class="{'bor':clicked==index}" @click="changeTab(index)">{{item}}</span>
            </li>
          </ul>
        </div>
        <div class="right">
          <component :is="componentName"></component>
          <!-- 组件一 -->
        </div>
      </div>
    </div>
    <home-page-footer></home-page-footer>
  </div>
</template>


<script>
import HomePageFooter from "../components/HomePageFooter.vue";

import Category0 from "../components/Category0.vue";
import Category1 from "../components/Category1.vue";
import Category2 from "../components/Category2.vue";
import Category3 from "../components/Category3.vue";

export default {
  components: {
    HomePageFooter: HomePageFooter,
    Category0: Category0,
    Category1: Category1,
    Category2: Category2,
    Category3:Category3,
    Category4:Category3,
    Category5:Category3,
    Category6:Category3,
    Category7:Category3,
    Category8:Category3,
    Category9:Category3,
    Category10:Category3,
    Category11:Category3,
  },
  data() {
    return {
      dataList: [
        "新品",
        "华为手机",
        "荣耀手机",
        "笔记本&平板",
        "智能穿戴&VR",
        "智慧屏",
        "耳机音箱",
        "专属配件",
        "通用配件",
        "生态产品",
        "增值服务",
        "智能计算",
        ""
      ],
      clicked: 0,

      componentName: "Category0"
    };
  },
  methods: {
    toProduct() {
      this.$router.push("product");
    },
    changeTab(index) {
      this.clicked = index;
      this.componentName = "Category" + index;
    }
  },
  activated() {
    this.$store.commit("currentPath", "classify");
  }
};
</script>

<style scoped>
.classify {
  width: 100%;
  height: 100%;
  font-size: 1rem;
  display: flex;
  flex-direction: column;
}
a {
  text-decoration: none;
}
li {
  list-style: none;
}
.wrap {
  width: 100%;
  height: 100%;
  background-color: white;
}
/* 上部 */
.header {
  width: 18rem;
  height: 2rem;
  /* background-color: pink; */
  padding-top: 5px;
  padding-left: 15px;
  display: flex;
  background-color: white;
}
.search {
  width: 14.6rem;
  height: 1.6rem;
  background-color: rgb(249, 249, 249);
  border-radius: 1rem;
  border: 1px solid rgba(0, 0, 0, 0.2);
  position: relative;
}
.search span {
  font-size: 20px;
  padding-left: 8px;
  line-height: 28px;
}
.da3 {
  display: inline-block;
  position: absolute;
  top: 0.25rem;
  left: 0.5rem;
}
.search input {
  display: inline-block;
  height: 1.5rem;
  position: absolute;
  font-size: 16px;
  color: red;
  left: 1.6rem;
  width: 11.5rem;
  border: none;
  background-color: rgb(249, 249, 249);
}
.icon {
  /* background-color: silver; */
  width: 1.9rem;
  height: 1.3rem;
  margin-top: 4px;
  margin-left: 5px;
  font-size: 25px;
  margin-left: 10px;
}

/* 主体 */
.main {
  display: flex;
  width: 100%;
  height: 27rem;
}
/* 左半部 */
.left {
  width: 27%;
  /* height: 718px; */
  /* background-color: rgb(222, 228, 141); */
  height: 26.5rem;
  overflow-y: auto;
}

/* 隐藏滚动条 */
.left::-webkit-scrollbar {
  display: none;
}

/* 右半部 */
.right {
  width: 73%;
  height: 100%;
  /* background-color: aqua; */
}
.left > .list > li {
  width: 4rem;
  height: 2.5rem;
  padding: 16px 0px;
  padding-left: 16px;
  font-size: 13.5px;
}
.bor {
  color: orangered;
  border-right: 2px solid orangered;
}
/* .left>.list>li span:hover{
    border-right:2px solid orangered;
} */

.left > .list > li span {
  display: inline-block;
  /* border-right:1px solid orangered; */
  width: 4rem;
  height: 0.9rem;
  /* background-color: palegoldenrod; */
}

/* 组件一 */
.zujian1 {
  overflow: hidden;
  height: 100%;
  overflow-y: auto;
}
.boxa1 {
  width: 12.6rem;
  height: 3.5rem;
  margin: 8px 8px 0px 12.5px;
}
.boxa2 {
  width: 12.6rem;
  height: 3.5rem;
  margin: 8px 8px 0px 12.5px;
}
.zujian1 .boxa1 a {
  display: inline-block;
  width: 12.6rem;
  height: 3.5rem;
}
.zujian1 img {
  width: 12.6rem;
  height: 3.5rem;
}

/* 标题之下 */
.title {
  width: 13.6rem;
  height: 2.1rem;
  /* background-color: sandybrown; */
  text-align: center;
  line-height: 2.1rem;
}
.con {
  width: 12.5rem;
  /* height: 562px; */
  /* background-color: slateblue; */
  margin-left: 12px;
}
.con ul {
  width: 12.5rem;
  /* height: 562px; */
  display: flex;
  justify-content: space-between;
  /* background-color: tomato; */
  flex-wrap: wrap;
}

.con img {
  width: 100%;
  height: 100%;
}
.sub01 {
  width: 50px;
  height: 50px;
  margin: 0 auto;
}
.primary {
  width: 3.3rem;
  height: 4.7rem;
  margin: 8px auto;
  /* background-color: thistle; */
}
.content01 {
  font-size: 12px;
  text-align: center;
  margin: 8px 0px;
}
</style>>
