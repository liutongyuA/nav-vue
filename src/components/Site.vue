<template>
  <div>
      <header>
      <form class="searchForm" method="get" action="https://www.baidu.com/s">
            <input name="wd" type="text">
            <button type="submit">搜索</button>
        </form>
    </header>
    <main>
        <ul class="siteList">
           <li class="content">
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
                    <div class="link">bilibili.com</div>
                </div>
            </a>
           </li>

           <li class="content">
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
                    <div class="link">bilibili.com</div>
                </div>
            </a>
           </li>
           <li class="content">
            <a href="https://www.bilibili.com/">
                <div class="site">
                    <div class="logo">
                        b
                    </div>
                    <div class="close">
                        <svg class="icon">
                            <use xlink:href="#i-close"></use>
                        </svg>
                    </div>
                    <div class="link">bilibili.com</div>
                </div>
            </a>
           </li>
           <li class="content">
            <a href="https://www.bilibili.com/">
                <div class="site">
                    <div class="logo">
                        b
                    </div>
                    <div class="close">
                        <svg class="icon">
                            <use xlink:href="#i-close"></use>
                        </svg>
                    </div>
                    <div class="link">bilibili.com</div>
                </div>
            </a>
           </li>
           
           <!-- 增加地址 -->
            <li class="last">
                <div class="site">
                        <svg class="icon">
                            <use xlink:href="#i-add"></use>
                        </svg>
                    <div class="text">新增网站</div>
                </div>
            </li>
        </ul>
    </main>
  </div>
</template>

<script>
export default {
    name:'Site',
}
</script>

<style>


/* 上面搜索 */
header{
    margin: 20px;
}
/* pc端 */
@media (min-width:500px) {
    header{
    margin-top: 60px;
    margin-bottom: 100px;
}
}
.searchForm{
    display: flex;
}
@media (min-width: 500px) {
.searchForm {
     max-width: 400px;
     margin: 0 auto;
}
}
.searchForm>input{
    width: 100%;
    margin-right: 10px;
    border-radius: 4px;
    height: 40px;
    /* 输入框颜色 */
    border: 1px solid #ddd; 
}
.searchForm>button{
    white-space: nowrap;
    padding:0 28px;
    color: white;
    background-color: #0282B9;
    border-radius:4px ;
    border: none;
}
/* 下面站点 */
.siteList{
    margin: 20px;
    display: flex;
    justify-content:space-between;
    flex-wrap: wrap;
}
.siteList>li{
    margin-bottom: 10px;
}
@media (min-width:500px){
    .siteList{
        justify-content: center;
    }
    .siteList>li{
        margin: 10px 20px;
    }
}
.siteList .site{
    width: 160px;
    padding: 20px 0;
    position: relative;
    border-radius: 4px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center; 
    /* 站点背景 */
    background-color:  transparent;
    border: 1px solid #eee;
}
/* 最后一个li添加 */
.site{
    cursor: pointer;
}
.siteList .site > .logo {
    width: 64px;
    height: 64px;
    /* 如果里面是字 */
    font-size: 64px;
    /* 大写字母 */
    text-transform: uppercase;
    display: flex;
    justify-content: center;
    align-items: center; 
}
img{width: 100%;}
.siteList .site > .icon{
    /* width: 1em; height: 1em; */
    width: 64px;
    height: 64px;
    /* 继承父元素的颜色 */
    fill: currentColor;
}
/* 鼠标移入关闭 */
.siteList .close{
    position: absolute;
    top: 5px;
    right: 10px;
    display: none;
}
.siteList .close> .icon{
    width: 1em;
    height: 1em;
}
.siteList > .content:hover .close{
    display:block;
}
</style>