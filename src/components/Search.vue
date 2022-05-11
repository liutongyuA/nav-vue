<template>
  <div class="search">
    <form class="searchForm" method="get" action="https://www.baidu.com/s">
      <div class="inputWrapper">
      <span class="seo"></span>
      <input placeholder="在baidu中搜索，或者输入一个网址" type="text" name="value" />
      </div>
      <button type="submit">搜索</button>
    </form>
  </div>
</template>

<script>

export default {
  name:'Search',

};
</script>

<style lang="less" scoped>
.search {
  padding: 10px;
  > .searchForm {
    display: flex;
    justify-content: center;
    >.inputWrapper{
      flex-grow: 1;
      margin-right: 5px;
      position: relative;
    >.seo{
      width: 1.5em;
      height: 1.5em;
      background-image: url('../assets/baidu.png');
      background-size: 100% 100%;
      position: absolute;
      top: 50%;
      left: 5px;
      transform: translateY(-50%);
    }
      > input {
        width: 100%;
        font-size: 16px;
        padding-left: 28px;
        margin-right: 10px;
        border-radius: 4px;
        height: 40px;
        /* 输入框颜色 */
        border: 1px solid #ddd;
      }
    }
    @media (min-width: 500px) {
      >.inputWrapper{
        max-width: 400px;
      }
  }
    > button {
      white-space: nowrap;
      padding: 0 28px;
      color: white;
      font-size: 14px;
      background:	rgb(64,158,255);
      border-radius: 10px;
      border: none;
        &:active ,&:hover {
    background-color: 	rgb(102,177,255);
    }
    }
  }
}
  @media (min-width:500px) {
    .search{
            // padding-top: 50px;
            // padding-bottom: 100px;
                margin-top: 60px;
    margin-bottom: 100px;
    }
  }
// header{
//     margin: 20px;
// }
/* pc端 */
// @media (min-width:500px) {
//     header{
//     margin-top: 60px;
//     margin-bottom: 100px;
// }
// }


</style>