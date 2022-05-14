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
