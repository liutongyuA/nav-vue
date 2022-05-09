<template>
  <div>
      <Search></Search>
      <siteList></siteList>
  </div>
</template>

<script>
import siteList from '@/components/siteList'
import Search from '@/components/Search'
export default {
    name:'Site',
    components:{
        siteList,
        Search
    }
}
</script>

<style scoped>


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

</style>