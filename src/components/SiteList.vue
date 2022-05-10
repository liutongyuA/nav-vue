<template>
  <div>
    <ul class="siteList">
      <li class="content" v-for="(i,index) in siteList" :key="index">
          <div class="site">
            <div class="logo">
              <img :src="`${i.url}/favicon.ico`" :onerror="imgDefault"/>
              <!-- <div v-else>B</div> -->
            </div>
            <div class="close">
              <svg class="icon">
                <use xlink:href="#i-close"></use>
              </svg>
            </div>
            <div class="text">{{i.text}}</div>
          </div>
      </li>

      <!-- <li class="content">
        <a href="https://www.bilibili.com/">
          <div class="site">
            <div class="logo">
              <img src="https://www.bilibili.com/favicon.ico" />
            </div>
            <div class="close">
              <svg class="icon">
                <use xlink:href="#i-close"></use>
              </svg>
            </div>
            <div class="text">bilibili.com</div>
          </div>
        </a>
      </li>
      <li class="content">
        <a href="https://www.bilibili.com/">
          <div class="site">
            <div class="logo">b</div>
            <div class="close">
              <svg class="icon">
                <use xlink:href="#i-close"></use>
              </svg>
            </div>
            <div class="text">bilibili.com</div>
          </div>
        </a>
      </li>
      <li class="content">
        <a href="https://www.bilibili.com/">
          <div class="site">
            <div class="logo">b</div>
            <div class="close">
              <svg class="icon">
                <use xlink:href="#i-close"></use>
              </svg>
            </div>
            <div class="text">谷歌</div>
          </div>
        </a>
      </li> -->
      <!-- 增加地址 -->
      <li class="last">
        <div class="site">
            <div class="logo">
             <svg class="icon">
            <use xlink:href="#i-add"></use>
          </svg>
            </div>

          <div class="text">新增网站</div>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
    name:'siteList',
    data() {
        return {
            siteList:[
                {
                    url:'https://www.baidu.com',
                    text:'百度'
                },
                {
                    url:'https://juejin.cn/',
                    text:'掘金'
                },
                {
                    url:'https://www.zhihu.com/',
                    text:'知乎'
                },
                {
                    url:'https://www.qq.com/',
                    text:'腾讯'
                },

            ],
            imgDefault:`this.src="${require('../assets/windbell.png')}"`,
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
    content: '';
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
      background-color: rgba(211, 211, 211,0.5);
      padding: 12px;
      border-radius: 50%;
      /* 如果里面是字 */
      font-size: 64px;
      /* 大写字母 */
      text-transform: uppercase;
      display: flex;
      justify-content: center;
      align-items: center;
      &>img {
      width: 100%;
    }
    }
    & .text{
        margin-top: 1em;
        font-family: 'Trebuchet MS', Arial, Helvetica, sans-serif;
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
 .last{
    .icon {
    width: 64px;
    height: 64px;
  }
 }
 > .content:hover .close {
  display: block;
}
}
// @media (min-width:500px){
//     .siteList{
//         justify-content: center;
//     }
//     .siteList>li{
//         margin: 10px 20px;
//     }
// }

</style>