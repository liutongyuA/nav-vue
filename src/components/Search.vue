<template>
  <div class="search">
    <form class="searchForm" method="get" action="https://www.baidu.com/s">
      <input name="wd" type="text" />
      <button type="submit">搜索</button>
    </form>
  </div>
</template>

<script>
export default {};
</script>

<style lang="less" scoped>
.search {
  padding: 20px;
  > .searchForm {
    display: flex;
    > input {
      width: 100%;
      margin-right: 10px;
      border-radius: 4px;
      height: 40px;
      /* 输入框颜色 */
      border: 1px solid #ddd;
    }
    > button {
      white-space: nowrap;
      padding: 0 28px;
      color: white;
      background-color: #0282b9;
      border-radius: 4px;
      border: none;
    }
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

// @media (min-width: 500px) {
// .searchForm {
//      max-width: 400px;
//      margin: 0 auto;
// }
// }
</style>