<template>
  <div>
    <ul class="siteList">
      <li class="content" v-for="(i, index) in siteList" :key="index">
        <div class="site" @click="go(i.url)">
          <div class="logo">
            <img :src="`${i.url}/favicon.ico`" :onerror="imgDefault" />
          </div>
          <div class="close" @click.stop="closeSite(i)">
            <svg class="icon">
              <use xlink:href="#i-chacha"></use>
            </svg>
          </div>
          <div class="text">{{ i.text }}</div>
        </div>
      </li>
      <!-- 增加地址 -->
      <li class="last">
        <div class="site" @click="addSite">
          <div class="logo">
            <svg class="icon">
              <use xlink:href="#i-add"></use>
            </svg>
          </div>
          <div class="text">新增网站</div>
        </div>
      </li>
    </ul>
    <!-- dialog -->
    <wb-dialog
        :visible="visible"
        title="设置标题"
        :showClose="true"
        :modal="true"
        @closeBefore="beforeClose"
    >
      <!--      <template slot="header"> 头部标题 </template>-->
      <template>
        <div class="a">
          <span style="margin-right: 1em">站点名称</span>
          <wb-input v-model="aaa"></wb-input>
        </div>
        <div class="b" style="margin-top:1em">
          <span style="margin-right: 1em">站点网址</span>
          <wb-input v-model="bbb"></wb-input>
        </div>
      </template>
      <template slot="footer">
        <wb-button @click="confirm">确认</wb-button>
        <wb-button @click="beforeClose(false)">取消</wb-button>
      </template>
    </wb-dialog>

  </div>
</template>

<script>
import {wbButton,wbDialog,wbInput} from 'windbell'
import 'windbell/dist/windbell.css'
export default {
  name: "siteList",
  data() {
    return {
      siteList: [
        {
          url: "https://www.baidu.com/",
          text: "百度",
        },
        {
          url: "https://juejin.cn/",
          text: "掘金",
        },
        {
          url: "https://www.zhihu.com/",
          text: "知乎",
        },
        {
          url: "https://www.qq.com/",
          text: "腾讯",
        },
      ],
      imgDefault: `this.src="${require("../assets/windbell.png")}"`,
      // dialog
       aaa: '',
      bbb:'',
      visible:false
    };
  },
  components:{
    wbButton,
    wbDialog,
    wbInput
  },
  created(){
    if(localStorage.getItem("siteKey") === null){
      // 第一次登录
       localStorage.setItem("siteKey",JSON.stringify(this.siteList))
    }else{
      let siteStr= JSON.parse(localStorage.getItem("siteKey"))
      this.siteList = siteStr
    }
  },

  mounted(){
      window.addEventListener('beforeunload',()=>{
          localStorage.setItem("siteKey",JSON.stringify(this.siteList))
      })
  },
  destroyed() {
    window.removeEventListener('beforeunload',()=>{
          localStorage.setItem("siteKey",JSON.stringify(this.siteList))
      })
  },
  methods: {
    //整理用户输入地址
    urlRule(url) {
      // 判断如果url没有http开头
      if (url.indexOf("http") !== 0) {
        console.log("输入地址有误，重新输入！");
      } else {
        return url
          .replace("https://", "")
          .replace("http://", "")
          .replace("www.", "")
          .replace(/\/.*/, "");
      }
    },
    //站点跳转
    go(e) {
      window.open(e);
    },
    //站点新增
    addSite() {
      // let content = prompt("请输入新增网址：");
      // // 后期用dialog改造这里
      // let addsiteList = {
      //   url: content,
      //   text: this.urlRule(content).charAt(0),
      // };
      // this.siteList.push(addsiteList);
      this.visible = true
    },
    //站点删除
    closeSite(i){
      let indexClose = this.siteList.indexOf(i)
      this.siteList.splice(indexClose,1)
    },
    // dialog
     confirm(){
      console.log(this.aaa,this.bbb);
       let addsiteList = {
        text: this.aaa,
        url: this.urlRule(this.bbb).charAt(0),
      };
      this.siteList.push(addsiteList);
      this.beforeClose(false)
    },
    //关闭前回调
    beforeClose(e){
      this.aaa=''
      this.bbb=''
      this.visible = e
    }
  },
};
</script>

<style lang="less" scoped>
.siteList {
  margin: 20px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  &::after {
    content: "";
    width: 110px;
  }
  > li {
    margin-bottom: 10px;
    // margin-right: auto;
  }
  .site {
    width: 110px;
    padding: 10px 0;
    position: relative;
    border-radius: 4px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    /* 站点背景 */
    // background-color: rgba(211, 211, 211,0.1);
    // pc端样式
    // cursor: pointer;
    > .logo {
      width: 64px;
      height: 64px;
      background-color: rgba(211, 211, 211, 0.5);
      padding: 12px;
      border-radius: 50%;
      /* 如果里面是字 */
      font-size: 64px;
      /* 大写字母 */
      text-transform: uppercase;
      display: flex;
      justify-content: center;
      align-items: center;
      & > img {
        width: 100%;
      }
    }
    & .text {
      margin-top: 1em;
      font-family: "Trebuchet MS", Arial, Helvetica, sans-serif;
      font-size: 14px;
      color: rgb(233, 231, 231);
    }
  }
  .close {
    position: absolute;
    top: 2px;
    right: 7px;
    display: none;
  }
  .last {
    cursor: pointer;
    .icon {
      width: 64px;
      height: 64px;
    }
  }
  > .content:hover .close {
    display: block;
  }
  > .content:hover .site {
    cursor: pointer;
    background-color: rgba(211, 211, 211, 0.1);
  }
}
@media (min-width: 500px) {
  .siteList {
    justify-content: center;
    &::after {
      content: "";
      width: 0px;
    }
    & > li {
      margin: 10px 20px;
    }
  }
}
</style>