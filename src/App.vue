<template>
  <div id="app">
    <Site></Site>
  </div>
</template>

<script>
import Site from '@/components/Site'
export default {
  name: 'App',
  components: {
    Site
  }
}
</script>

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    list-style: none;
}
*:before,
*:after {
    box-sizing: border-box;
}
a{
    color: inherit;
    text-decoration: none;
}
#app{
background-image:url(./assets/wallhaven.png);
background-position: center center;
background-repeat: no-repeat;
background-attachment: fixed;
background-size: cover;
background-color: #464646;
}
</style>
